# Hubot Yammer Adapter

## Description

This is the [Yammer](http://www.yammer.com) adapter for hubot that allows you to
send a message to your Hubot and he will reply to you.

## Installation

* Add `hubot-yammer` as a dependency in your hubot's `package.json`
* Install dependencies with `npm install`
* Run hubot with `bin/hubot -a yammer -n the_name_of_the_yammer_bot_account`

### Note if running on Heroku

You will need to change the process type from `app` to `web` in the `Procfile`.

## Usage

You will need to set some environment variables to use this adapter.

### Heroku

   heroku config:add HUBOT\_YAMMER\_KEY="key" HUBOT\_YAMMER\_SECRET="secret" HUBOT\_YAMMER\_TOKEN="token" HUBOT\_YAMMER\_TOKEN\_SECRET="secret"

### Non-Heroku environment variables

   export HUBOT\_YAMMER\_KEY="key"
   export HUBOT\_YAMMER\_SECRET="secret"
   export HUBOT\_YAMMER\_TOKEN="token"
   export HUBOT\_YAMMER\_TOKEN\_SECRET="secret"

## How to get your credential informations

An easy way to get your access codes is to use [nyam](https://github.com/csanz/node-nyam).

Nyam is a node.js CLI tool wich can help you to setup Yammer authorizations.

1. First, log on to Yammer and get your own application keys.

    https://www.yammer.com/\<DOMAIN\>/client\_applications/new

1. Install nyam

    npm install nyam -g

Warning: Actually, nyam need a 0.4.x version of node.js. You may want to look at [nvm](https://github.com/creationix/nvm)

1.  To override nyam configuration with your own app keys create the following file:

    ~/.nyam\_keys

and add the following

    {
        "app_consumer_key": "<CONSUMER KEY HERE>",
        "app_consumer_secret": "<CONSUMER SECRET HERE>"
    }

1. Then, start the setup process to give hubot-yammer access to an account 

    nyam -s

1. Finally, run nyam with a verbose level to display all the informations you need

    nyam --verbose

## Contribute

Just send pull request if needed or fill an issue !

## Copyright

Copyright &copy; Aurélien Thieriot. See LICENSE for details.

## Thanks

To [Mathilde Lemee](https://github.com/MathildeLemee) from wich I shamefully fork the code