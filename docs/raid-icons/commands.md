# Commands

One command, and it runs entirely on your client — it is never sent to the server, so it works
everywhere, including on servers where you have no permissions at all.

## `/raidicons`

Reports what the mod can currently see. Run it **while aiming at a raid den crystal**: the most
useful line it prints is what the game says that block actually is.

```
Raid Icons
  den block: cobblemonraiddens:raid_crystal_block
  layers: minimap=true worldmap=true
  scan: 4096 chunks examined, 3 den(s) known
  nearest den: fighting tier 5 at 214, 71, -388 (36m) boss=klinklang_terafighting
  looking at: cobblemonraiddens:raid_crystal_block [raid_type=fighting, raid_tier=tier_five,
    is_active=true] - MATCHES the den block
```

Every line answers a different question, and together they narrow any "my dens aren't showing up" to
one cause:

| Line | What it tells you |
|---|---|
| `den block` | Whether Raid Dens is installed at all. `NOT in the registry` means nothing can ever be found. |
| `layers` | Whether Xaero's minimap and world map were found. Both `false` means the mod has nowhere to draw. |
| `scan` | How much ground has been covered and how many dens are known. `0 chunks examined` means the scan is not running. |
| `nearest den` | The closest den the mod knows, with its type, tier, distance and boss. |
| `looking at` | The aimed block's registry id and every blockstate property it carries, verbatim — and whether the mod recognises it. |

The report also goes to your log (`logs/latest.log`), so you can read it afterwards, or paste it into
a [bug report](../reporting.md) without having taken a screenshot at the right moment.

!!! tip "The line that matters"

    Everything this mod does rests on one assumption: that the crystal in front of you is the block
    and the properties it expects. `looking at` confirms or destroys that assumption in one step. If
    it says `is NOT the den block` while you are aiming at a den, that is the whole bug report.
