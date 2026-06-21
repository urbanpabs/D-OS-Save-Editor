# D-OS Save Editor

A save editor for **Divinity: Original Sin – Enhanced Edition**.

> ⚠️ This editor only works for *Divinity: Original Sin – Enhanced Edition*. Do **not** use it for the original *Divinity: Original Sin* or for *Divinity: Original Sin 2*.

This is a fork of [Se7enthSeal/D-OS-Save-Editor](https://github.com/Se7enthSeal/D-OS-Save-Editor), which is itself based on the original [AnthonyZJiang/D-OS-Save-Editor](https://github.com/AnthonyZJiang/D-OS-Save-Editor), with a number of fixes and new features (see [Changes in this fork](#changes-in-this-fork)).

---

## Download & install

1. Go to the [**Releases**](../../releases) page and download the latest `D-OS-Save-Editor-vX.Y.Z.zip`.
2. Extract the zip anywhere (keep all the files together — the `.exe` needs the DLLs and the `ItemTemplates` folder next to it).
3. Run **`D-OS Save Editor.exe`**.

Requirements: Windows with **.NET Framework 4.8** (already present on up-to-date Windows 10/11).

> 💾 **Always back up your save before editing.** Copy the save folder somewhere safe first. Edited saves are not guaranteed to be reversible.

---

## How to use

1. **Launch** the editor and **open your save** — pick the savegame from the list.
2. **Choose a character** from the drop-down at the top (party members each have their own inventory and stats).
3. Make changes on the tabs (below).
4. Click **Save**. The editor writes your changes back into the `.lsv` save file.
5. Load the save in-game.

### Tabs

- **Stats** — vitality, experience, attribute/ability/talent points, etc.
- **Abilities** — points in each ability (e.g. *Crafting*, *Blacksmithing*, *Lucky Charm*, the combat/magic schools). Abilities cap at **5** in-game; gear can raise the effective value on top of that.
- **Traits** — personality trait values.
- **Talents** — learned talents.
- **Inventory** — edit existing items: rarity (Common → Unique), durability, and **Modifiers** (boosts). Right-click the Modifiers box to add/copy/delete a modifier.
- **Add Items** — add new items to the selected character's inventory.

### Adding items

1. On the **Add Items** tab, use the category checkboxes and the **Filter** box to find an item.
   - Items are listed by their **internal template name**, not their in-game display name — e.g. a lockpick is `TOOL_LockPick_A` and a Tormented Soul is `LOOT_Soul_Tormented_A`. Search by a keyword (e.g. `tormented`) and make sure the matching category (e.g. *Loot*) is checked.
2. Click an item to add it to the list on the right; set the **amount** and, for weapons/armor, pick a **rarity**.
3. Click **Apply changes** — the item appears in the **Inventory** tab as a *(pending add)* row.
4. Click **Save**, then load the game. The item will be in that character's inventory.

> Tip: make sure the correct character is selected in the drop-down *before* adding items — items go to whichever character is currently selected.

### Editing durability / modifiers on added equipment

A freshly-added weapon or piece of armor comes in at full durability and can be re-edited (durability, rarity, modifiers) after you **Save and reopen** the file.

---

## Changes in this fork

- Add new items to a character's inventory, with a per-item **rarity** picker.
- Added items now reliably **persist into the game** (fixed a flag that caused them to be purged on load).
- Added weapons/armor get a proper durability/stats block, and durability is editable for equipment that previously had none.
- Queued item additions are shown in the Inventory list before saving.
- Several crash fixes and clearer error messages.

---

## Building from source

Open `D-OS Save Editor.sln` in Visual Studio (with the .NET desktop workload) and build in **Release**, or from a developer command prompt:

```
nuget restore "D-OS Save Editor.sln"
msbuild "D-OS Save Editor/D-OS Save Editor.csproj" /p:Configuration=Release
```

Releases are built and published automatically by the [`Release` GitHub Actions workflow](.github/workflows/release.yml) whenever a `vX.Y.Z` tag is pushed.

---

## Contributors

- [urbanpabs](https://github.com/urbanpabs) — maintainer of this fork (in-game item persistence, rarity/durability editing, crash fixes, release automation, docs)

Contributions welcome — open an issue or pull request.

## Credits

- [Norbyte](https://github.com/Norbyte) for [LSLib / LSTools](https://github.com/Norbyte/lslib).
- [AnthonyZJiang](https://github.com/AnthonyZJiang) for the original save editor.
- [Se7enthSeal](https://github.com/Se7enthSeal) for the fork this build is based on.
