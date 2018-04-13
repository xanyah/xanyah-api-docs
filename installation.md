---
description: How to install and run the project
---

# Installation

## Requirements

You will need the following programs:

* Docker
* Docker Compose
* Yarn
* Ruby

## Instructions

Clone the repo:

```
$ git clone git@github.com:xanyah/xanyah-api.git
```

Once you've cloned the repo, enter the directory:

```text
$ cd xanyah-api
```

You will need to setup your environment variables. The list is available in _.env.example_:

```text
$ cp .env.example .env
```

{% hint style="info" %}
You will need to create an Amazon Web Services account and an S3 bucket to use variants import if needed.
{% endhint %}

Install all your dependencies:

```text
$ bundle install   // For Ruby dependencies
$ yarn             // For npm dependencies
```

You will now need to start your database, using **Docker Compose**:

```text
$ docker-compose up
```

And run all your migrations:

```text
$ rake db:migrate
```

## Start the development server

```text
$ rails s
```



