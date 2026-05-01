conway-clock
============

A Conway's-Game-of-Life clock for the conference-room TV. Loads in a browser, fast-forwards a digital-clock GoL pattern (by Dim) to the current wall-clock time, and reloads every minute to stay in sync.

Live: https://malcolmocean.github.io/conway-clock/

This is a fork of [copy/life](https://github.com/copy/life) (BSD-2-Clause) with patches to support time-based fast-forward and a kiosk default. The clock pattern is from [Dim's codegolf.se answer](https://codegolf.stackexchange.com/questions/88783/build-a-digital-clock-in-conways-game-of-life), bundled locally as `examples/conway-clock-ampm.rle`.

Kiosk URL params
-

The bare URL (`/`) loads the clock in kiosk mode with sensible defaults. To customize:

- `?gen=N` — fast-forward to generation N (debug/calibration)
- `?clock=1&gpm=N` — sync to system clock at N gens per displayed minute
- `?epoch=HH:MM[:SS]` — wall-clock time gen 0 represents (default 12:00)
- `?starttime=HH:MM[:SS]` — override system clock for testing
- `?refresh=N` — reload every N seconds
- `?noui=1` — hide the toolbar/statusbar
- `?fps=N` and `?step=N` — engine tick rate

Calibration: the clock pattern advances 11,520 generations per displayed minute. The first "12:01" appears at gen ≈ 26,500, so the kiosk default uses `epoch=11:58:10` to center the displayed minute on the wall minute.

`window.life` and `window.drawer` are exposed for console-based calibration.

License
-
BSD-2-Clause, inherited from upstream copy/life. See `LICENSE`.
