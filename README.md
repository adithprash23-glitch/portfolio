# portfolio

My personal site. It's one HTML file (`index.html`), no framework and no build step, hosted on Vercel.

What's on it:

- The synth I'm building right now, an STM32 that reads MIDI and knobs and an FPGA that makes the sound. Still in progress, so the code and a demo video go up once it actually works.
- A version of that synth that runs in the browser. You can play it with a mouse, your laptop keyboard (bottom row Z to M is the lower octave, top row Q to U is the upper one), or a real MIDI keyboard if you're on Chrome or Edge.
- A small 8051 emulator, based on the trainer kit we used in my high school electronics lab where you typed in hex opcodes by hand.
- My experience, coursework, and how to reach me.

## How the browser synth works

Each of the 4 voices has a 32-bit counter (the phase) that gets a fixed number added to it every sample. The bigger that number, the faster the counter wraps around, so the higher the pitch. The top bits of the counter turn into the waveform: used directly for a saw, just the top bit for a square, or as an index into a 256 entry table for a sine. This is the same way the oscillators on the FPGA are going to work, which is why it's done this way instead of using the browser's built in oscillators.

After that each voice goes through an ADSR envelope, all 4 get mixed, and the mix goes through a one-pole lowpass filter. The audio runs in an AudioWorklet so it doesn't stutter when the page is busy.

## Running it

Open `index.html` in a browser. Sound only starts after you click or press a key since browsers block audio before that.

## Adding Arduino projects

There's an `ARDUINO_PROJECTS` list near the top of the script in `index.html`. Add an entry and an Arduino section shows up under Experience.
