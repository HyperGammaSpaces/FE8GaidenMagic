# Gaiden Magic for FE8

#### (Character-based magic use through a separate menu)

## NOTE: This repository is deprecated in its current form. It is being preserved as a proof of concept.

In Fire Emblem Gaiden and its remake Fire Emblem Echoes, magic wielders did not keep their spells in their inventories as tomes, but rather as options in a selectable menu that they could cast anytime. Units would learn spells when they hit a particular level and could use it on player phase anytime, so long as they had enough hit points to cast. The drawback included to balance this was the cost of the spell being taken directly from the user's HP rather than from the tome's durability. This hack enables units who can use attack magic to use "innate" magic that is not kept in their inventory.

### How to use

- Clone or download this repo
- Place a copy of the [latest version of Event Assembler](https://github.com/FireEmblemUniverse/Event-Assembler) in the root directory
- Place a clean FE8 rom in the project directory named "FE8_clean.gba"
- Run "MAKE HACK full.cmd"

All characters who use magic in vanilla FE8 have some spell lists defined already. For staff-locked units, they can access it when they promote (units must have a weapon rank in Anima, Light or Dark to access the B.Magic menu). Additionally, I defined a spell list for Eirika if you just want to test it out right away - in that case, you can give her an Anima weapon rank or change her into a Mage using FEBuilder or a custom Prologue chapter event.

### Release notes
This is version 1.0. I have not yet tested for compatibility with the Skill System, but it probably won't play nice; thankfully this is a buildfile project so there's the option of moving things around should you choose to use both. Additionally, this overwrites the Play command in the unit menu, so it will break Bards (unused in fe8) or any other command that decided to overwrite there. Future releases will repoint this menu option table so that nothing gets overwritten. HP cost for the spells are determined by the Weapon EXP given per use, which is hacky but efficient.

### Known issues

- Magic menu can only be selected on player phase; if the unit does not have a fallback weapon in their inventory they will be unable to counterattack on enemy phase. All vanilla characters defined in the SpellAssociationTable can wield magic normally so in normal gameplay it wouldn't make a difference. (It would just give you a free attack on player phase if for some reason your weapon breaks.)
- When selecting a unit to move it, if they do not have a usable weapon in their inventory their attack range won't be drawn.
- HP bars don't animate the cost of casting a spell during battle.

### Future releases

- Fix attack range display for unit movement range.
- Allow unequipped units to select the first spell in their spell list to counterattack.
- Pop-up displays when a unit learns a spell.
- Display a unit's known spells on the status screen.
- Display spell with grey text if a unit knows a spell but can't cast it due to HP.
- Implement a separate lookup table for spell HP cost to allow decoupling from the Weapon EXP value.
- Repoint the unit menu so that Play is usable again

### Special thanks
- FEU Discord server for advice and bug bashing
- [SkillSystem repo](https://github.com/FireEmblemUniverse/SkillSystem_FE8) where the battle procs tweaks were adapted from
