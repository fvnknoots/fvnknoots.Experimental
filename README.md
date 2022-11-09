fvnknoots.Experimental
================================================================================

Experimental balance mod lead by ???

Goals
--------------------------------------------------------------------------------

  1. ???
  2. ???
  3. ???

Constraints
--------------------------------------------------------------------------------

  1. ???
  2. ???
  3. ???

Change summary
--------------------------------------------------------------------------------

  * BTK = bullets to kill

### CAR

  * Near damage: 25 -> 1 (4 -> 100 BTK)
  * Far damage: 13 -> 1 (7 -> 100 BTK)
  * Very far damage: 10 -> 1 (10 -> 100 BTK)

### Alternator

  * Near damage: 35 -> 20 (3 -> 5 BTK)
  * Far damage: 18 -> 13 (6 -> 8 BTK)
  * Very far damage: 14 -> 10 (8 -> 10 BTK)

### Volt

  * Near damage: 25 -> 17 (4 -> 6 BTK)
  * Far damage: 15 -> 12 (7 -> 9 BTK)
  * Very far damage: 12 -> 10 (9 -> 10 BTK)

### R97

  * Near damage: 20 -> 13 (5 -> 8 BTK)
  * Far damage: 12 -> 8 (9 -> 13 BTK)
  * Very far damage: 10 -> 7 (10 -> 15 BTK)

### R101

  * Near damage: 25 -> 17 (4 -> 6 BTK)

### R201

  * Near damage: 25 -> 17 (4 -> 6 BTK)

### Flatline

  * Near damage: 30 -> 20 (4 -> 5 BTK)

### Spitfire

  * Near damage: 35 -> 25 (3 -> 4 BTK)
  * Far damage: 25 -> 20 (4 -> 5 BTK)
  * Very far damage: 20 -> 17 (5 -> 6 BTK)

### EVA-8

  * Near damage: 200 -> 150

### RE-45

  * Near damage: 20 -> 15 (5 -> 7 BTK)
  * Far damage: 13 -> 12 (7 -> 9  BTK)
  * Very far damage: 9  -> 8 (12 -> 13 BTK)

### Kraber

  * Damage: 350 -> 800
  * Ricochets: 2 -> 200

### P2016

  * Near damage: 30 -> 20 (4 -> 5 BTK)
  * Far damage: 20 -> 17 (5 -> 6  BTK)
  * Very far damage: 15 -> 13  (7 -> 8 BTK)

### Melee

  * No lock-on
  * Range: 60 -> 1 (1 -> 0 meters)
  * Damage: 100 -> 0

### A-Wall

  * Shield health reduced by 50% (1000 -> 500)

### Gravity star

  * Pull time reduced by 50% (2.0 -> 1.0 seconds)
  * Push strength: 125 -> 300

### Electric smoke

  * Radius (both inner and outer) increased by 1 meter (50 -> 100, 210 -> 250)

### Arc grenade

  * Radius (both inner and outer) increased by 1 meter (75 -> 125, 350 -> 400)

Development
--------------------------------------------------------------------------------

### Damage range to bullets needed for kill

Make changes based on how many bullets are needed for kill,
because that's most noticeable for the player.

| Damage range | Bullets to kill |
|--------------|-----------------|
| 100+         | 1               |
| 50 - 99      | 2               |
| 34 - 49      | 3               |
| 25 - 33      | 4               |
| 20 - 24      | 5               |
| 17 - 19      | 6               |
| 15 - 16      | 7               |
| 13 - 14      | 8               |
| 12           | 9               |
| 10 - 11      | 10              |
| 9            | 12              |
| 8            | 13              |
| 7            | 15              |
| 6            | 17              |
| 5            | 20              |
| 4            | 25              |
| 3            | 34              |
| 2            | 50              |
| 1            | 100             |


### Weapon code names

[Link](https://r2northstar.gitbook.io/r2northstar-wiki/hosting-a-server-with-northstar/dedicated-server#weapons)

### Harmony VPK tool

[Link](https://github.com/harmonytf/HarmonyVPKTool/releases/tag/1.2.0)

  1. Open `vpk/englishclient_mp_common.bsp.pak000_dir.vpk` in your Titanfall 2 install directory
  2. In the VPK, open:
     - `RootDir/scripts/weapons` for keyvalue files
     - `RootDir/scripts/vscripts/weapons` for Squirrel scripts
  3. Unpack the file somewhere on your PC
  4. Copy the file under `reference/` and:
     - `keyvalues/scripts/weapons`, if it's a keyvalue file
     - `mod/scripts/vscripts/weapons`, if it's a Squirrel script
  5. Leave the file under `reference/` as is, changes are made in `keyvalues/scripts/weapons` or `mod/scripts/vscripts/weapons`

### Change tracking

Use `./diffs.sh` or `./changes.sh` to track changes. You can also search for a single file
by passing a substring, eg.:

    $ ./changes.sh car

Make sure `./diffs.sh` includes only actual changes, not anything else (like whitespace changes and such).

### Editing

_Always_ keep `README.md` and [experimental.nut](./mod/scripts/vscripts/experimental.nut)
up-to-date with changes.

When editing a file under `keyvalues/scripts/weapons`, put a comment after the line explaining
the change like this:

  * `CHANGE/NERF: old value -> new value (explanation)`, if it's a nerf
  * `CHANGE/BUFF: old value -> new value (explanation)`, if it's a buff

Example:

```
"damage_near_value"     "14" // CHANGE/NERF: 25 -> 14 (4 -> 7 bullets)
"damage_far_value"      "10" // CHANGE/NERF: 13 -> 10 (7 -> 10 bullets)
"damage_very_far_value" "8"  // CHANGE/NERF: 10 -> 8 (10 -> 12 bullets)
```
