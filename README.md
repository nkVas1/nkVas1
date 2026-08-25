# N Guhl · `nkVas1`

I build desktop tools for Windows in Rust — mostly by taking a capability the
platform already has and making it reachable.

Every project below started the same way: something useful was already there,
buried behind a driver panel, an undocumented API, or an interface nobody
finished. The work is turning it into something a person can actually use.

---

## Building

**[Resonance](https://github.com/nkVas1/Resonance)** — super-resolution for the
whole desktop, not just games.
Your GPU can render the OS above your panel's native resolution and downsample
it back, and the hardware has shipped this for years as NVIDIA DSR/DLDSR. It
lives in a control panel, breaks DPI scaling, and has no automation. Resonance
gives it one hotkey, automatic DPI compensation, per-app rules, and a switch
that always reverts itself.
`Rust · Tauri 2 · Svelte 5 · NVAPI`

**[diskovery](https://github.com/nkVas1/diskovery)** — where the disk space went.
Reads the NTFS master file table directly instead of walking directories, so a
full drive resolves in seconds. GPU treemap, BLAKE3 duplicate detection, and a
cleanup advisor that ranks findings by how much it would cost to be wrong.
`Rust · Tauri · React · TypeScript`

**[enjoystick-windows](https://github.com/nkVas1/enjoystick-windows)** — Windows 11
driven entirely from a gamepad.
A Steam Deck-style overlay for PS and Xbox controllers, for when the screen is
across the room.
`C++`

---

## How I work

- **Measure before and after.** A change is justified by a number, not by
  reasoning about it. When I reported that a slicer bug altered printed output,
  the evidence was 542,925 differing toolpath moves, not an argument that it
  should.
- **Say what was not checked.** Every report separates what is verified from
  what is assumed. Silence about coverage reads as a claim of coverage.
- **Small, separable changes.** Three narrow pull requests instead of one broad
  one, so a reviewer can take part of it.
- **Record the decision, not just the code.** Architecture decisions go in
  `docs/adr/` together with the alternatives that lost, and why.
- **Trust the eye.** Twice I have found defects that passing automated checks
  did not see. A test suite proves what it was asked; it says nothing about the
  rest.

---

## Contributing upstream

Open pull requests against [OrcaSlicer](https://github.com/OrcaSlicer/OrcaSlicer),
after its command line silently produced prints that did not match the
configuration it was given:

| Pull request | What it fixes |
|---|---|
| [#15370](https://github.com/OrcaSlicer/OrcaSlicer/pull/15370) | JSON numbers and booleans were discarded without a word, so writing `"precise_outer_wall": 0` switched the feature **on** |
| [#15371](https://github.com/OrcaSlicer/OrcaSlicer/pull/15371) | 183 shipped presets could not be loaded at all, because one field was compared case-sensitively |
| [#15372](https://github.com/OrcaSlicer/OrcaSlicer/pull/15372) | Misspelled settings were accepted in silence; adds `--strict-config` |

---

## Client work

Commercial delivery runs through **OdinLab Studios**, my digital studio —
production sites and tooling for paying clients rather than demos. Most recent:
a full rebuild for a concrete and precast manufacturer in St. Petersburg, live
at [snabservis-sz.ru](http://snabservis-sz.ru/) (Astro, React islands, Three.js,
PHP/MySQL back end, deployed from GitHub Actions).

Client source stays private. The work does not.

---

## Also

Applied acoustics and parametric CAD: a twin-chamber Mesoamerican duct flute
designed from transfer-matrix acoustics rather than from a reference photograph,
with the archaeology cited; room-acoustic modelling checked against a microphone
instead of against itself.

Rust · C++ · Python · TypeScript · Tauri · Windows internals

📍 Germany · [nkvas1.github.io/Resonance](https://nkvas1.github.io/Resonance/)
