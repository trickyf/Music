# Booth Studio

A music app that runs in your browser. Open `index.html` and press a button to start the audio. There's no build step and nothing to install.

## What's in it

**Live code.** Write patterns in a small Strudel-style language and hear them loop. Edit while it plays and press `Ctrl+Enter` (`Cmd+Enter` on Mac). The new version starts at the next bar.

```js
setbpm(124)
$: s("bd*4, ~ cp ~ cp, [~ hh]*4")
$: note("<[~ a1]*4 [~ a1]*4 [~ f1]*4 [~ g1]*4>").s("bass").lpf(1400)
$: chord("<Am Am F G>").s("pad").gain(0.7)
$: note("[a4 c5 e5 c5]*2").s("pluck").degradeBy(0.25).gain(0.35)
```

The reference beside the editor lists every function. Mini-notation supports `~` rests, `[a b]` to squeeze notes into one step, `<a b>` to alternate each bar, `a*4` to repeat, `a!3` to copy, `a?` for maybe, and `a, b` to play both at once.

**Keys and looper.** Play with your computer keyboard (`A` to `'` are the white keys, `W` to `P` the black keys, `Z`/`X` change octave) or tap the on-screen piano. It names the chord you're holding, inversions included. **Chord mode** turns each key into a full chord from the key you pick, so anyone can play a progression. **Record loop** layers what you play over 1, 2 or 4 bars, in time with the code and the drum machine.

**Chord finder.** Load a track onto a deck and it finds the chords beat by beat, shows them above the waveform, and estimates the key with its Camelot code (for example `4A`). **Chords to code** turns the next 8 bars of chords, from a deck or from your loop, into a `chord("<…>")` line in the editor.

**Two decks and a mixer.** Each deck starts with a demo loop. You can also drop in your own MP3, WAV, OGG or M4A file. Decks have cue, loop, tempo ±20%, tap tempo, BPM detection and Sync (matches tempo and beat). The mixer has 3-band EQ, a filter that sweeps from low-pass to high-pass, channel faders and an equal-power crossfader.

**Drum machine.** A 16-step grid with kick, snare, clap, hat and open hat. It shares its tempo with the live code.

All sounds are synthesized with the Web Audio API, so there are no sample downloads.
