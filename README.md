# Reddit Place Bot for r/Mexico

This is a bot for the Reddit [/r/place](https://www.reddit.com/r/place/) event of 2017 April Fools Day.

Bot created by [Zequez](https://github.com/Zequez/reddit-placebot)

## Installation

You need to have [NodeJS installed, click here to download](https://nodejs.org/es/download/)

Once you have it installed, follow the next steps:

Open a new terminal/cmd and type (if you have windows, you can download the zip from github instead of doing git clone):
```
git clone https://github.com/alexherce/reddit-placebot
cd reddit-placebot (or go to the directory where you downloaded it)
npm install
```

## Configuration

Change `users.example.json` to `users.json` and add your reddit username and password
of your account and all your throwaways. You can add more than one.

If you previously ran the bot and you changed the users in `users.json`, erase `queues.json` and `cookies.json` and run it again.

## Target Drawing

If you run it as it is, is going to connect to this [repo](https://github.com/alexherce/reddit-placebot) and try to draw
the [`official_target.bmp`](https://raw.githubusercontent.com/alexherce/reddit-placebot/master/official_target.bmp). This image defends the current r/mexico letters and flag. If you want to add something to the image to draw or defend, ask in the Discord.

If you don't want to do that you can open `config.js` and
set `autoupdateRemoteTarget: false`. This will make it use `target.bmp` instead. You have to edit the `target.bmp` to draw what you want.

To help draw and defend the triangle flag in the middle, opne `config.js` and change `REMOTE_TARGET_URL` to `https://raw.githubusercontent.com/alexherce/reddit-placebot/master/official_triangle_flag.bmp`

Every time it's time to place a pixel the bot will download the board
(and latest remote target) and find the first pixel that doesn't match
the target, and fill it with the correct color.

## About Colors

Since I honestly couldn't figure out how to make transparent BMP files I just
set it so that the color `#ff00ff` is considered transparent. Anything transparent
will be ignored.

You have to use the exact same colors as the board (see `colors.js` for RGB codes) or the app is gonna throw
an error, it's not smart enough to guess the colors based on similarity.

## Usage

To run, simply type the next line in the terminal/cmd:

```
  npm run start
```

It'll keep keep drawing forever and if it can't draw anymore it's gonna
wait until something breaks and fix it.

To stop, use CTRL + C.

## License

MIT
