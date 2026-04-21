# Fotoarmonio — Instrument Reconstruction

Reconstructed April 2026 from primary sources:
- `archive/2019-officium/officium-proposta copy.pdf` (2012 proposal, v0.5)
- `archive/2019-officium/Palermo.pd` (Pure Data patch, 2016 BIAS Palermo)
- `archive/2019-officium/doc-palermo/` (installation photos)
- Author's memory

## What it is

Fotoarmonio is a **light/sound installation**: a reflecting water basin
through which sound modulates the geometry of light. Environmental sound,
generated to exploit the natural resonances of the site, becomes first
light and then geometry, using caustics produced by periodic motion of
the water surface.

Fotoarmonio is used inside the larger performance *Officium Tenebrarum*
(40-min movement/sound/light piece, 3 performers: musician, dancer,
master of ceremony). It can also stand alone as an installation, as at
BIAS Biennale Palermo 2016 and Selinunte 2017.

The codename in the source files is **Light-Shaker**, which describes
the mechanism literally: sound shakes water, water shapes light.

## Physical elements

- Shallow reflecting water basin
- Transducer coupled to the basin, driven by low-frequency signal (~38 Hz)
- Central light source ("la luce centrale del fotoarmonio"), projecting
  through/onto the water
- Microphone capturing ambient room sound
- Sound output (stereo) for the tonal layer audible to the audience

## Signal flow (from Palermo.pd, 2016)

Four signal paths, mixed into a 4-channel `mixer~` → stereo `output~`:

1. **Shaker carrier** — `osc~ 39`, amplitude-controlled knob+slider, sent
   to physical transducer. This vibrates the water. DO NOT exceed
   ~3000 Hz: "or it brakes." (sic — physical damage to the transducer.)
2. **Tonal left** — `osc~ 150` amplitude-modulated by `osc~ 2` tremolo,
   level+AM-depth controlled by knob+slider.
3. **Tonal right** — identical structure to (2), independent controls.
4. **Microphone** — `adc~` into an envelope follower; ambient sound of
   the space enters the modulation chain.

Four envelope followers (`env~ - 100`) send amplitude-as-control
signals (`toLVU`, `toRVU`, `toPVU`, `toSIGVU`) — despite the naming,
these are not display meters but modulation sources. Likely used to
cross-couple signals or drive lamp intensity.

## Parameter notes from the patch

- Carrier frequency knob range: 20–50 Hz. Tuning note in the patch:
  "find the carrier frequency first (around 38 Hz) then you can add
  harmonics of mic input to have fun."
- Tremolo oscillators at 2 Hz.
- Tonal oscillators at 150 Hz.
- The correct operating procedure is **tune the shaker to the basin's
  resonance first**, then layer audible tones and mic input.

## Artistic frame

From the proposal (2012):
- Venue: historical, enclosed, circular, atypical — caverns, natural
  grottoes, halls with high ceilings, historic palazzi.
- Darkness: performed at night or in complete darkness.
- Audience enters in procession, each carrying a lit candle.
- Candles are extinguished one by one during the performance; on the
  last, the audience screams.
- Texts: free interpretation of Antonin Artaud's *Théâtre du Séraphin*,
  with Italian and French symbolist poetry.
- Music: Marin Marais' *La Follia d'Espagne* adapted for cello (or
  flute, or viola da gamba).
- Power: can run entirely on solar-charged batteries — no grid required.

## Lineage

- 2012 — Proposal v0.5 written (Amsterdam, 26 Nov 2012).
- 2014 — First documented performance, Palermo, Dimora Oz, 30 Nov 2014.
  (Photo: `fotoarmnio2014.jpg`.)
- 2016 — BIAS Biennale, Palermo. PD patch `Palermo.pd` is from this
  edition. (Photo: `fotoarmonio-2016-BIAS.jpg`, plus `doc-palermo/`.)
- 2017 — BIAS Biennale, Selinunte.

## Open questions for the 2026 restart

- Exact transducer model used in 2016? (not in the patch — hardware
  survives only in memory)
- Light source: single central lamp? underwater? overhead?
- Basin dimensions and material?
- Calibration procedure: was the 38 Hz value specific to the 2016
  basin, or a general order of magnitude?
- Relationship of the four `env~` channels to lamp intensities —
  if any.
