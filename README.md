# Alice Studio

A tiny reusable drawing studio, extracted from **Picture the Patient**.

The principle is simple: one drawing engine, different customers. The engine owns drawing behaviour; each consuming project supplies its own configuration and context.

## v0.1

- pencil, eraser and fill
- three configurable line widths
- configurable colour palette
- undo and clear
- local autosave
- PNG save/share
- touch, stylus and mouse input
- responsive phone layout

## Configuration

`config/default.json` contains the studio defaults. Colours are deliberately data rather than hard-coded UI. To change a colour, edit its `hex` value. Add/remove/reorder entries to change the palette.

A customer can eventually supply its own config, for example Picture the Patient or AutistiAlice, without changing the drawing engine.

## Next

1. Test the extracted studio against the current Picture the Patient behaviour, especially stylus input and fill.
2. Add named/selectable palette files.
3. Make the standalone studio an installable offline PWA.
4. Change Picture the Patient to consume Alice Studio rather than owning its drawing engine.

**Methodology:** dicking about until something interesting occurs.
