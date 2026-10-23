# Changelog

## [0.1.0]

### Added
- A standalone Freeverb-style reverb running in the browser via an
  AudioWorklet: 8 parallel comb filters into 4 series allpass filters per
  channel, independently tuned.
- Eight controls: Size, Damp, Predelay (up to 150ms), Width (mono to
  exaggerated stereo), Low Cut, High Cut, Tone, Mix.
- A screen showing input/output level history and a simple two-bar
  meter.
- A synthesized demo drum/bass/chords loop with real transients, good
  for hearing the tail rather than a wash.
- Presets, undo/redo, A/B, light/dark theme, fullscreen — the same
  infrastructure as Egret EQ, Egret Comp and Egret Guitar.
