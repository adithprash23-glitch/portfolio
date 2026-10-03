# portfolio

My personal website. It's a single HTML file, no framework and no build step.

What's on it:

- the synth I'm building right now (STM32 + FPGA)
- a version of the synth that runs in the browser, so you can play it with your computer keyboard or a MIDI keyboard (MIDI only works in Chrome/Edge)
- a small 8051 emulator, based on the trainer kit we used in my high school electronics lab
- my experience and coursework

## Running it

Just open `index.html` in a browser. Sound only starts after you click or press a key, browsers block audio before that.

## Deploying

It's hosted on Vercel. Pushing to `main` redeploys it.

## Adding Arduino projects

There's an `ARDUINO_PROJECTS` list near the top of the script in `index.html`. Add an entry and the section shows up on the page.
