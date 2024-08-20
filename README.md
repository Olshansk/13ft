# 13 Feet Ladder <!-- omit in toc -->

A site similar to [12ft.io](https://12ft.io) but is self hosted and works with
websites that 12ft.io doesn't work with.

- [What is this?](#what-is-this)
- [How does it work?](#how-does-it-work)
- [How do I use it?](#how-do-i-use-it)
  - [Using Docker](#using-docker)
    - [From Source](#from-source)
    - [From an Image](#from-an-image)
  - [Using Python](#using-python)
    - [Environment Setup (One Time)](#environment-setup-one-time)
    - [Environment Usage (Every Time)](#environment-usage-every-time)
    - [Instruction](#instruction)
  - [1. Go to the website at the url shown in the console](#1-go-to-the-website-at-the-url-shown-in-the-console)
  - [2. Click on the input box](#2-click-on-the-input-box)
  - [3. Paste your desired url](#3-paste-your-desired-url)
  - [4. Voilà you now have bypassed the paywall and ads](#4-voilà-you-now-have-bypassed-the-paywall-and-ads)
  - [Alternative method](#alternative-method)

## What is this?

This is a simple self hosted server that has a simple but powerful interface to block ads, paywalls, and other nonsense. It is especially useful for sites like medium, new york times which have paid articles you normally cannot read. Now I do want you to support the creators you benefit from but if you just wanna see one single article and move on with your day, this might be helpful.

## How does it work?

It pretends to be GoogleBot (Google's web crawler) and gets the same content that google will get. Google gets the whole page so that the content of the article can be indexed properly and this takes advantage of that.

## How do I use it?

### Using Docker

Pre-requisites:

1. `docker`
2. `docker-compose`
   First, clone the repo to your machine then run the following commands:

#### From Source

```sh
git clone https://github.com/wasi-master/13ft.git
cd 13ft
docker-compose up
```

#### From an Image

The image is also available from [DockerHub](https://hub.docker.com/r/wasimaster/13ft "docker pull wasimaster/13ft") or [ghcr.io](https://github.com/wasi-master/13ft/pkgs/container/13ft "docker pull ghcr.io/wasi-master/13ft:0.2.3") so the command `docker pull wasimaster/13ft` also works.

### Using Python

Make sure you have [python](https://python.org) installed on your machine.

```sh
git clone https://github.com/wasi-master/13ft.git
cd 13ft
```

#### Environment Setup (One Time)

```bash
make env_create
$(make env_source)
make pip_install
```

#### Environment Usage (Every Time)

```bash
$(make env_source)
make pip_freeze
```

#### Instruction

Run the following and follow the steps below

```sh
make start_server
```

### 1. Go to the website at the url shown in the console

![step 1 screenshot](screenshots/step-1.png)

### 2. Click on the input box

![step 2 screenshot](screenshots/step-2.png)

### 3. Paste your desired url

![step 3 screenshot](screenshots/step-3.png)

### 4. Voilà you now have bypassed the paywall and ads

![step 4 screenshot](screenshots/step-4.gif)

### Alternative method

You can also append the url at the end of the link and it will also work. (e.g if your server is running at `http://127.0.0.1:5001` then you can go to `http://127.0.0.1:5001/https://example.com` and it will read out the contents of `https://example.com`)

This feature is possible thanks to [atcasanova](https://github.com/atcasanova)
