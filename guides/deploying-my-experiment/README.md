---
description: >-
  How to deploy your experiment.
---

# Deploying Your Experiment

{% hint style="warning" %}
This tutorial does require some knownledge of Linux and servers. We are working
on a simpler experience for deployment. Meanwhile, if it's too much, come
talk to us in
[Slack](https://join.slack.com/t/empirica-ly/shared_invite/zt-1fb34yq47-YlgYUJmXJAdv7QmHsa_fdw).
{% endhint %}

This tutorial describes how to deploy Empirica using any server or VM provider.
Empirica is a single command, and uses a embedded database, so there is only one
executable to install.

First, you need a server. There are thousands of different options on how to get
running here. One quick and easy service we can recommend is Digital Ocean's
Droplets: https://docs.digitalocean.com/products/droplets/quickstart/

You will need to be able to connect to the sever over SSH. If you are not
familiar, [here's an introduction](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys).

## Bundling your experiment

Bundling your experiment is the task of building all the code you've created for
your experiment, and packaging it, along with the configuration, into a
compressed "bundle" file.

To do so, run, at the root of your experiment:

```sh
empirica bundle
```

This should create a file like `[name-of-your-experiment].tar.zst`. This is your
bundled experiment. This is what you will deploy to your server. You should not
add this to your code repository.

## Setting up the server

You will need the empirica binary:

```sh
curl https://install.empirica.dev | sh -s
```

## Running the experiment

You will need to send your experiment bundle to the server. For example, using
`scp`:

```sh
scp myexperiment.tar.zst someuser@example.com:~
```

And finally, on the server, run the experiment with:

```sh
empirica serve myexperiment.tar.zst
```

Your experiment will be available on the address of that machine on port 3000.

## Optional: setup a reverse proxy

We recomend you use a Reverse Proxy to expose your experiment to the internets
and secure connections with HTTPS. A great tool for this is
[Caddy](https://caddyserver.com). Check out the installation instructions
[here](https://caddyserver.com/docs/install).

You will need a domain name in order to use HTTPS (encrypted connections). We
will not go into much detail here, but you can find many registrars online, such
as Google Domains, Cloudflare Registrar, Namecheap or Hover.

Then you will need to configure your domain name to point to your server. This
is also beyond the scope of this guide, but you should be able to lookup the
documentation of your hosting provider (e.g. Digital Ocean) and you Registrar
(e.g. Google Domains) to figure out how to point your domain name to your server
using either an A Record or CNAME Record.

Once your domain name is setup (we will use `www.example.com` in our example),
you can simply run:

```sh
caddy reverse-proxy --from www.example.com --to localhost:3000
```

This will setup the HTTPS certificate and redirect all incoming traffic to
empirica.

## Saving the database

The data in empirica will be stored in `.empirica/local/tajriba.json`. Copy that
file to a safe place after running your experiment. You can take as many
snapshots of you data as you wish by simply copying that file every so often.
