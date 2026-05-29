# Credits

This project stands on the work of several authors. Full credit to them.

| Component | Author | Source |
| --- | --- | --- |
| Original addon (retail **iTargetingFrames**) | **Ironi** | https://www.curseforge.com/wow/addons/itargetingframes |
| WotLK 3.3.5a backport | **Cheeta** (**CH33T4**) | https://github.com/CH33T4/iTargetingFrames |
| `AwesomeWotlkLib.dll` (Retail Nameplate API for 3.3.5a) | **FrostAtom** | https://github.com/FrostAtom/awesome_wotlk |

## This fork (vanvonlj/iTargetingFrames-wotlk)

Maintained by **Lucas Van Vonderen** ([@vanvonlj](https://github.com/vanvonlj)). Changes on top of the upstream backport:

- **Fix:** click-to-target no longer breaks after `/reload`. Upstream applied click bindings only inside a spec-detection branch (`if iTF.specID then` in `CheckTalents`); on characters/clients where spec detection returns `nil`, bindings were never applied on load. Bindings are now applied on load regardless of spec, and the per-class binding table is guarded where indexed.
- **Feature:** an **ElvUI** layout profile that mirrors ElvUI UnitFrames — pulls ElvUI's live media (`E.media.normTex` / `normFont` / `bordercolor` / `backdropcolor`), name left / health right inside the bar, 1px border; inherits threat colors and everything else from the Default profile.
- **Convenience:** bundles the "fixed nameplate units" build of `AwesomeWotlkLib.dll` so it doesn't have to be sourced separately. This binary is **FrostAtom's** work (see above), included only for convenience.

## Licensing note

Neither the upstream addon nor `awesome_wotlk` states an explicit license. This fork is published in the same spirit (a free community addon) with attribution preserved. If any original author requests removal of their work, it will be removed promptly.
