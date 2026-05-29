# iTargetingFrames (WotLK) — reload-fix fork

> **Fork of [CH33T4/iTargetingFrames](https://github.com/CH33T4/iTargetingFrames)** (WotLK 3.3.5a backport by *Cheeta* of the [retail addon by *Ironi*](https://www.curseforge.com/wow/addons/itargetingframes)). All credit for the addon goes to them.
>
> **What this fork changes:** fixes click-to-target silently breaking after a `/reload`. Upstream only applied the click bindings inside a spec-detection branch (`if iTF.specID then` in `CheckTalents`), so on characters/clients where spec detection returns `nil` (e.g. a low-level/untalented character), bindings were never applied on load — targeting worked right after manually assigning a key, then died on the next reload. This fork applies bindings on load regardless of spec detection and guards the per-class binding table where it's indexed. See the commit history for the exact diff.

Displays nameplate units in a clickable grid. Backport for WotLK (3.3.5a) from [Retail Addon by Ironi](https://www.curseforge.com/wow/addons/itargetingframes). 

Requires a patched client with AwesomeWotlkLib.dll for the Retail Nameplate API — get it from [FrostAtom/awesome_wotlk](https://github.com/FrostAtom/awesome_wotlk). If units are shown more than once, use the "fixed nameplate units" build of the DLL. (This fork does not redistribute the binary.)

Use /itf or /itargetingframes to open config window.

# Feature list
![Image](https://github.com/user-attachments/assets/d64e81c9-bdd9-4a0c-b8cf-8fff65895f9a) ![Image](https://github.com/user-attachments/assets/180e71d9-9653-4166-bec5-39b328be42d7)
## Clickable unitframes
- Unit Name
- Cast bar
- Health bar
- Debuffs (with spell name or spell id blacklisting)
    + Duration text
    + Stack count
    + Flashing for < X duration 
- Click-to-cast (general, class, spec specific bindings)
    + Cast spell
    + Macro text

## Conditionals for indicators:
- Range (Spells in rangeSpells.lua)
    + Interrupt range 
    + Max DPS range 
    + Max utility 
- Unit out of combat
- Current target
- Focus target
- Threat
    + Losing aggro
    + Gaining aggro
    + Aggro 
- Priority NPC
- Custom
    + Usage: (Template for Health threshold, Magic buff)
      ```
      function(unitID)
        if ... then
          return true
        end
      end
## Indicators
- Glow
- Border
- Healthbar
- Frame opacity 

![Image](https://github.com/user-attachments/assets/355e1e07-7268-442e-9497-026bd22578f3)

# How to install the addon
1. Download this fork. [[Download](https://github.com/vanvonlj/iTargetingFrames-wotlk/archive/refs/heads/main.zip)]
2. Open the Zip package and copy (Ctrl+C) the `iTargetingFrames` folder over to your addons folder (Interface/Addons). 
3. Install the AwesomeWotLK client patch from [FrostAtom/awesome_wotlk](https://github.com/FrostAtom/awesome_wotlk) (run `AwesomeWotlkPatch.exe`). If units appear more than once, use the "fixed nameplate units" build of `AwesomeWotlkLib.dll`.
