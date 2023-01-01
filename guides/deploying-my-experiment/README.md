---
description: How to deploy your experiment.
---

# Deploying Your Experiment

{% hint style="warning" %}
This tutorial does require some knowledge of Linux and servers. We are working on a simpler experience for deployment. Meanwhile, if it's too much, talk to us in [Slack](https://join.slack.com/t/empirica-ly/shared\_invite/zt-1fb34yq47-YlgYUJmXJAdv7QmHsa\_fdw).
{% endhint %}

This tutorial describes how to deploy Empirica using any server or VM provider. Empirica is a single command and uses an embedded database, so there is only one executable to install.

First, you need a server. There are thousands of different options on how to get running here. One quick and easy service we can recommend is [Digital Ocean's Droplets](https://docs.digitalocean.com/products/droplets/quickstart/).

You will need to be able to connect to the server over SSH. If you need to become more familiar, [here's an introduction](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys).

## Bundling your experiment

Bundling your experiment is the task of building all the code you've created for your experiment and packaging it, along with the configuration, into a compressed "bundle" file.

To do so, run at the root of your experiment:

```
empirica bundle
```

This should create a file like `[name-of-your-experiment].tar.zst`. This is your bundled experiment. This is what you will deploy to your server. You should not add this to your code repository.

## Setting up the server

You will need the empirica binary:

```
curl https://install.empirica.dev | sh -s
```

## Running the experiment

Just so you know, you will need to send your experiment bundle to the server. For example, using `scp`:

```
scp myexperiment.tar.zst someuser@example.com:~
```

And finally, on the server, run the experiment with:

```
empirica serve myexperiment.tar.zst
```

Your experiment will be available at the address of that machine on port 3000.

## Optional: setup a reverse proxy

We recommend you use a Reverse Proxy to expose your experiment to the internet and secure connections with HTTPS. An excellent tool for this is [Caddy](https://caddyserver.com). Check out the installation instructions [here](https://caddyserver.com/docs/install).

You will need a domain name to use HTTPS (encrypted connections). We will not go into much detail here, but you can find many registrars online, such as Google Domains, Cloudflare Registrar, Namecheap, or Hover.

Then you will need to configure your domain name to point to your server. This is also beyond the scope of this guide. Still, you should be able to look up the documentation of your hosting provider (e.g., Digital Ocean) and your Registrar (e.g., Google Domains) to figure out how to point your domain name to your server using either an A Record or CNAME Record.

Once your domain name is set up (we will use `www.example.com` in our example), you can run:

```
caddy reverse-proxy --from www.example.com --to localhost:3000
```

This will set up the HTTPS certificate and redirect all incoming traffic to empirica.

## Saving the database

The data in empirica will be stored in `.empirica/local/tajriba.json`. Copy that file to a safe place after running your experiment. You can take as many snapshots of your data as you wish by copying that file every so often.

You can also export the data from the server by running the export command. See the export section on the [managing-the-data.md](../managing-the-data.md "mention") page.
