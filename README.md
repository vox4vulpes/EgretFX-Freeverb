# Egret Freeverb

**[Use it in your browser](https://vox4vulpes.github.io/EgretFX-Freeverb/)** ·
part of the [Egret FX Bundle](https://github.com/vox4vulpes/EgretFX)

A standalone Freeverb-style reverb — the same comb+allpass tank built for
[Egret Guitar](https://github.com/vox4vulpes/EgretFX-Guitar)'s Reverb
pedal, on its own, with more control over it: Size, Damp, Predelay,
Width, Low Cut, High Cut, Tone and Mix. It runs entirely in the browser
via the Web Audio API — no plugins, no install. Open `index.html` in any
modern browser.

See [CHANGELOG.md](CHANGELOG.md) for what's shipped. A VST3 plugin and
standalone app (matching [Egret EQ](https://github.com/vox4vulpes/EgretFX-EQ),
[Egret Comp](https://github.com/vox4vulpes/EgretFX-Comp) and
[Egret Guitar](https://github.com/vox4vulpes/EgretFX-Guitar)'s JUCE build)
is next.

## The controls

- **Size** — how long the tail takes to decay
- **Damp** — how quickly the tail's high end dies away, independent of
  Size
- **Predelay** — a gap between the dry sound and the reverb's arrival (up
  to 150ms), the way a real room's first reflection is never instant
- **Width** — narrows or widens the tail's stereo spread; 0% collapses it
  to mono, 100% is the tank's natural stereo image, up to 200% exaggerates
  it
- **Low Cut** / **High Cut** — shape what gets fed into the tank in the
  first place, so a boomy bass note doesn't make the reverb muddy or a
  bright hi-hat doesn't make it harsh
- **Tone** — a gentle lowpass after the tank, for an overall darker or
  brighter tail
- **Mix** — blends the reverb with the dry signal

The screen shows input/output level over the last few seconds — simpler
than [Egret Comp](https://github.com/vox4vulpes/EgretFX-Comp)'s, since a
reverb doesn't have a transfer curve to draw. Click a knob's value to
type one. `Space` plays the source.

## How it works

8 parallel comb filters feed into 4 series allpass filters per channel —
the classic Freeverb topology — independently tuned, not copied
constants. The two channels are decorrelated with a small delay-length
offset rather than two fully independent tanks, which is what gives
Width something real to narrow or widen. Every knob glides into its new
value over ~50ms, so nothing clicks or zippers while you turn it.

The demo source is a short synthesized drum/bass/chords loop, in the same
spirit as [Egret Comp](https://github.com/vox4vulpes/EgretFX-Comp)'s —
real transients and gaps between hits are the clearest way to actually
hear a reverb tail, rather than a wash of sustained tone.

## License

[GNU AGPLv3](LICENSE). Copyright (c) 2026 vox4vulpes
