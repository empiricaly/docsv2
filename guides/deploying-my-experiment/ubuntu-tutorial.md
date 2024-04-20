---
description: >-
  This will is a tutorial explaining how to setup Empirica an Ubuntu 23.10
  Droplet on Digital Ocean.
---

# Ubuntu tutorial

This will go through all the steps needed to deploy an Empirica experiment in a generally secure manner, how to update your experiment, and how to retrieve your data. We are using Digital Ocean, which is relatively easy to use, but you can use any hosting provider and the steps will be similar if you use Ubuntu 22+.

This tutorial does assume a few things:

* You have minimal Linux, command line, and ssh experience. If you don't check out some quick intro tutorials on Youtube.
* You have a domain name. A subdomain on empirica.app can be provided, see Setup your domain below for details.

### Bundle your experiment

At the root of your experiment, run:

```sh
empirica bundle
```

This will create a file called `myexperiment.tar.zst` where `myexperiment` is the name of your experiment or `empirca`. This file will be useful later in the process.

### Create your dropplet on Digital Ocean

1. Sign up to [Digital Ocean](https://www.digitalocean.com)
2. Click `Create` in the top left, then `Droplets`
3. Choose a region close to you ; datacenter doesn't matter much, leave the default
4. For the image selection, choose `Ubuntu` then `23.10 x64`
5. For size, choose `Basic`, then `Premium AMD`, then `4GB/2CPU` or `8GB/4CPU` depending on your needs. Generally, you can get by with 2 CPUs, espcially during development, and you can always upgrade your droplet later.
6. `Enable automated backup...`, daily, doesn't hurt
7. For SSH keys, if you know what's up, add your key, if you don't, follow [this tutorial](https://docs.digitalocean.com/products/droplets/how-to/add-ssh-keys/).
8. Enable `Add improved metrics...`
9. Quantity: 1
10. Hostname: you choose (e.g. myexperiment), this is unrelated to your domain name, it's mostly just the name in your Digital Ocean admin UI.
11. Click `Create Droplet`
12. Wait for the Droplet to start, and note down the IP address

### Setup your domain

#### Your own domain

If you have a access to a domain name, we'll assume you know how to setup an A Record (name is the domain or subdomain name you want to use, the value is the IP address of your Droplet, and for TTL either automatic/default, or 5 min if you expect to change the address soon).

You might want to double check your domain is configured correctly (it can take a few minutes to propagate). On macos and linux you can use dig:

```sh
dig @8.8.8.8 mydomainname.com A
```

#### empirica.app subdomain

If you do not have a domain name, you can contact Nicolas P. on Slack with the subdomain on empirica.app you'd like to use (e.g. mycoolexperiment.empirica.app). Please provider 2-3 options that are not too generic (e.g. `experiment` is too generic) so we don't conflict, and the IP address of your Droplet.

A couple of notes:

* please do not do anything illegal on your domain. We are not responsible for anything sketchy you do on your subdomain
* if you're taking down your experiment, please let us know so we can cleanup the DNS entry. We reserve the right to clear the subdomain if we haven't heard from your in a year or two

### Setup your server

SSH into your server using the IP address from your Droplet. For example:

```sh
 ssh root@123.123.123.123
```

{% hint style="info" %}
For the more experienced users, these instructions are installing things as root. We understand that is not ideal. Setting up a separate user is beyond the scope of this tutorial. The nature of Empirica deployments is to be usually short lived and relatively low risk. You are welcome to setup a non-privileged user if you prefer. If you wish to contribute improvements to this tutorial with such instructions, that would be simple enough for the casual users, contributions are welcome!
{% endhint %}

#### Install Empirica

To install empirica on your server, run:

```sh
curl -fsS https://install.empirica.dev | sh
```

#### Install caddy

Caddy is the reverse proxy that will enable HTTPS on your experiment. To install, run the following commands:

```sh
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https curl
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

#### Setup Empirica

We want Empirica to reload automatically in case of a crash, a server restart, or an update. For that we will create a few folders and configuration files.

First, create a folder for the deployment at the root of your user (where you ssh-ed in). We will use a directory called `empirica`:

```sh
mkdir empirica
```

We will create 2 files to start and restart empirica using `systemctl`. First, run:

```sh
sudo nano /etc/systemd/system/empirica.service
```

In this file, paste the following:

```systemd
[Unit]
Description=Empirica Service
After=network.target

[Service]
Type=simple
WorkingDirectory=/root/empirica
ExecStart=/usr/local/bin/empirica serve /root/empirica/empirica.tar.zst
Restart=always
RestartSec=5
KillSignal=SIGINT
TimeoutStopSec=10
Environment="PATH=/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin"

[Install]
WantedBy=multi-user.target
```

Save the file (with nano, ctrl+o then Enter) and exit (ctrl+x).

We will then create a restarter file:

```sh
sudo nano /etc/systemd/system/empirica-restart.service
```

And paste the following:

```systemd
[Unit]
Description=Empirica restarter
After=network.target

[Service]
Type=oneshot
ExecStart=/usr/bin/systemctl restart empirica.service

[Install]
WantedBy=multi-user.target
```

We will then create a watcher file:

```sh
sudo nano /etc/systemd/system/empirica.path
```

And paste the following:

```systemd
[Unit]
Description=Watch /root/empirica/empirica.tar.zst for changes

[Path]
PathChanged=/root/empirica/empirica.tar.zst
Unit=empirica-restart.service

[Install]
WantedBy=multi-user.target
```

Save and exit nano. This file will restart empirica when the empirica bundle changes.

Run the following to register these 2 files:

```sh
sudo systemctl daemon-reload
```

#### First deployment

Next, we'll upload your Empirica experiment bundle (the `.tar.zst` file we created in the first step) from your machine to your server. You can do that with `scp` (replace myexerpiment with the name of your bundle and the IP address with your Droplet IP address):

```sh
scp myexperiment.tar.zst 123.123.123.123:~/empirica/empirica.tar.zst
```

We can now start empirica like so:

```sh
sudo systemctl enable --now empirica.service
```

Check that it's running as expected:

```sh
curl -v localhost:3000
```

It should return a bunch of html with an HTTP code 200 (`HTTP/1.1 200 OK`).

#### Setup Caddy

Delete the existing configuration for Caddy:

```sh
rm /etc/caddy/Caddyfile
```

And add a new one:

```sh
sudo nano /etc/caddy/Caddyfile
```

With the following, where the domain name if the domain name you setup:

```
mydomain.empirica.app {
        reverse_proxy localhost:3000
}
```

And restart caddy:

```sh
systemctl restart caddy
```

It might take a minute for the HTTPS certificates to generate. Go to your domain in your browser, and if all goes well, your experiment is deployed, with HTTPS.

#### Restart empirica on changes

We will enable our restarter units:

```sh
sudo systemctl enable --now empirica-restart.service
sudo systemctl enable --now empirica.path
```

Now, next time you bundle and upload again, empirica should restart automatically. See [#update-your-experiment](ubuntu-tutorial.md#update-your-experiment "mention") below.

### Run experiment

#### Access the admin

Go to `/admin` on your domain in the browser. You will be asked for a username and password. You can find the default username (`admin` by default) and password (randomly generated with your new project) in your project in `.empirica/empirica.toml` on your local machine. You can change or add more users from that file and redeploy.

#### Export the data

On your server, the data will be in `~/empirica`, and you can run the following from root:

```sh
cd empirica
empirica export
```

To copy the data back to your machine, you can run, from your machine (`*` will pull all the exports, you can specify the exact zip file your want instead) :

```sh
scp 123.123.123.123:~/empirica/*.zip .
```

#### Update your experiment

To update your experiment, bundle and scp again from your local machine:

```sh
empirica bundle
scp myexperiment.tar.zst 123.123.123.123:~/empirica/empirica.tar.zst
```

You will need to reload the browser to see the changes. It does not reload the page automatically as it does in local development mode.

### Administration tasks

#### Stop, restart, or start empirica manually

```sh
systemctl stop empirica
systemctl restart empirica
systemctl start empirica
```

#### View logs

```sh
journalctl -u empirica -f
```
