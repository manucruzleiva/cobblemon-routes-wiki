# The Icons

Every raid den the mod has seen is drawn where it stands, as the icon of its **tera type**. A den is
found the moment its chunk reaches your client, and the marker disappears the moment the crystal
does — mine one and it is gone from the map on the same tick.

The markers are not waypoints. They are drawn by the mod straight onto Xaero's maps, so they never
enter your waypoint list, cannot be dragged out of place, and leave nothing behind when you uninstall.

## On the minimap

The icon sits over the minimap at 36×36 pixels — big enough to read at a glance in the corner of the
screen, small enough that a cluster of dens does not bury the terrain.

A den that is outside the minimap's view is **not drawn at all**. Xaero pins an off-view marker to
the rim of the minimap, which is the right behaviour for a waypoint you chose to watch and the wrong
one for every den in the world: the border would fill up with icons for dens hundreds of blocks away.

## On the world map

The same icon, at 48×48 — the world map is a whole screen, and an icon sized for the minimap reads
as a speck on it.

### The tooltip

Hover a den on the world map and it names itself in two lines:

```
Klinklang
★★★★★ Fighting
```

The Pokémon waiting in the den comes first, because that is what you are deciding on. Below it, the
star tier and the tera type, written in that type's own colour.

If your client has not yet received the den's contents, the species line is **left out** rather than
filled with a placeholder. A tooltip that said "Unknown" would be claiming the den has no boss, which
is a different fact from not knowing yet.

## What gets an icon

Everything the scan finds, until you say otherwise. Three [filters](configuration.md) narrow it down:

- **Star tier** — hide everything below the tier you are hunting.
- **Tera type** — list the types you care about and the rest stop being drawn.
- **Active only** — hide the dens that are not currently live.

A den whose tera type the mod does not recognise still gets a marker. A den you cannot classify is
worth more on the map than no den at all.

## Why icons appear as you walk

The mod reads dens out of the chunks your game has already been sent — it asks the server for
nothing and adds no network traffic. Chunks you have never loaded hold no dens as far as it is
concerned, so the map fills in behind you as you explore rather than all at once.

That also means a den someone else builds far away appears the next time you are near it, and the
scan re-checks what it knows continuously, so a den that changes is never remembered wrong.
