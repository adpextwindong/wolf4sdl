wl_draw.cpp compiles with

```
g++ wl_draw.cpp -c -fpermissive
```

with SDL2 headers just dumped in.

# Deps

ThreeDRefresh is where the magic begins.

wl_play.cpp -> wl_game.cpp -> wl_draw.cpp

g++ -MM reports these (only wl_ files included.)
```
wl_play.o: wl_play.cpp wl_def.h version.h
 wl_menu.h wl_cloudsky.h wl_shade.h
wl_game.o: wl_game.cpp wl_def.h wl_menu.h
wl_draw.o: wl_draw.cpp wl_def.h wl_menu.h wl_cloudsky.h wl_atmos.h \
 wl_shade.h
```

Files needed in order seen from wl_play onwards:
- wl_def.h
- wl_cloudsky.h
- wl_shade.h
TODO

ifdef stuff to note:
    USE_SHADING

g++ wl_play.cpp wl_game.cpp wl_draw.cpp to look at linker errors while we trim it down.
