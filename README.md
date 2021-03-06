# WhatsTrapp

![WhatsTrapp video](https://media.giphy.com/media/1gQ65LmOcgLwe1XKWl/giphy.gif)

## Introduction
*WhatsTrapp* is a tool for analyzing and dumping WhatsApp accounts.

## Requirements

- Node.js >= 8.0
- Yarn
- Docker
- Docker Compose

## Installation

Clone the repository:
```
$ git clone git@github.com:Wicker25/whatstrapp.git
$ cd whatstrapp/
```

Install all the dependencies for the project:
```
$ yarn
```

## Trying it out

Launch the *WhatsTrapp* server with:
```
$ yarn start
```

Then open your browser at http://127.0.0.1:8025/ and wait until the QR code has been loaded.

Launch the target's *WhatsApp* and, from the main menu, select "WhatsApp Web".

Finally, take a picture of the QR code and enjoy it!

## Data Analysis

Open *Kibana's Discover* page at http://127.0.0.1:5601/app/kibana#/discover.

![Kibana Discover page](https://user-images.githubusercontent.com/500733/46049959-4e859f80-c129-11e8-8bfc-747da987567f.png)

You can start a new *Search* or open one of the default ones from the menu on the right.

![kibana](https://user-images.githubusercontent.com/500733/46050467-2ea3ab00-c12c-11e8-829d-494af87078ce.png)

## Architecture

The *WhatsTrapp*'s architecture consists of a *Puppeteer*, *Puppets*, and *Clients*:

![WhatsTrapp architecture](https://user-images.githubusercontent.com/500733/45647051-d54cd380-babc-11e8-8906-d277456ed211.png)

- The *Puppeteer* launches the browser instance by using [Google Puppeteer](https://github.com/GoogleChrome/puppeteer) and injects a *Puppet* into it;
- The *Puppet* is a JavaScript that performs actions in the [WhatsApp Web](https://web.whatsapp.com/) page;
- The *Client* is the user interface used by the attacker for performing the hack.

All of the components communicate with each other via *WebSocket*.
