I build desktop tools for Windows in Rust, usually by taking a capability the
platform already has and making it reachable — [Resonance](https://github.com/nkVas1/Resonance)
productizes the super-resolution buried in your GPU driver, and
[diskovery](https://github.com/nkVas1/diskovery) reads the NTFS master file
table directly so a full drive resolves in seconds instead of minutes.

Commercial work runs through **OdinLab Studios**, my digital studio — most
recently a full rebuild for a concrete manufacturer, live at
[snabservis-sz.ru](http://snabservis-sz.ru/). Client source stays private.

I try to justify changes with a number rather than an argument, and to say
plainly what I did *not* check. Recently that meant three fixes to
[OrcaSlicer](https://github.com/OrcaSlicer/OrcaSlicer)'s command line, which was
silently printing something other than the configuration it was handed:
[#15370](https://github.com/OrcaSlicer/OrcaSlicer/pull/15370) — a JSON `0` was
discarded, which switched the feature it disabled **on**;
[#15371](https://github.com/OrcaSlicer/OrcaSlicer/pull/15371) — 183 shipped
presets were unloadable over one case-sensitive comparison;
[#15372](https://github.com/OrcaSlicer/OrcaSlicer/pull/15372) — misspelled
settings were accepted without a word.

Also applied acoustics: a twin-chamber Mesoamerican duct flute designed from
transfer-matrix acoustics rather than from a reference photograph.

Rust · C++ · Python · TypeScript · Tauri · Windows internals — 📍 Germany
