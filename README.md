# Supernatural Threat Defence Force #

## About ##

STDF is a cooperative multiplayer strategy game that revolves around
defending oncoming paranormal attacks to your location.

You might just make it if you are able to hold out a few more minutes
while the white wizard assembles a magical protection barrier. Working
as a team is essential to stand any chance of survival.


## License ##

Supernatural Threat Defence Force is free software: you can
redistribute it and/or modify it under the terms of the GNU General
Public License as published by the Free Software Foundation, either
version 3 of the License, or (at your option) any later version.

See [COPYING](./COPYING) for details.


## Status ##

This game is a work in progress. Some of the basic data structures are
in place and random generation of player cards, enemies, war paths and
location sections is more or less implemented, but there is no logic
tying everything together into a playable game.

The logic around location section generation could use some
improvement, since sections are only aware of other sections they were
directly connected to during creation. To illulstate this, imagine a
grid representing a location where each cell represents a section. If
section A creates B to the east and C to the south, and C creates D to
the east, B and D won't be accessible to each other despite being
directly next to each other. This may be undesirable.

## Demo ##

```
player = Player()
print(player)

enemy = Enemy()
print(enemy)

war_paths = []
for path in list(range(0, 3)):
    war_paths.append(WarPath())
    print(war_paths[path])

location = HauntedLocation()
print(location)
```

The above example code will produce the following:

```
Player:
  Mana: 5
  Cards:
    - Action: heal, Movement: north/south
    - Action: attack, Movement: east/west
    - Action: conjure mana, Movement: east/west
    - Action: heal, Movement: east/west
    - Action: conjure mana, Movement: north/south
    - Action: conjure mana, Movement: north/south
Enemy: Vengeful Spirit
Damage: 4
Health: 7
Defence: 1
Speed: 4
- - - - - - - - X - - Y - - Z
- - X - - Y - - - - - - - - Z
- X Y - - - - - - - - - - - Z
Location: Ghost Town
Sections:
  - E
Sections:
  - W
  - E
  - N
Sections:
  - W
  - S
Sections:
  - E
Sections:
  - W
  - N
Sections:
  - S
```
