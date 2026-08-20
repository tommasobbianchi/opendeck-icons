# opendeck-icons

Key art for [opendeck-shortcuts](https://github.com/tommasobbianchi/opendeck-shortcuts), so the
same glyph is not generated twice on every machine.

Each file is a **96×96 PNG** at `icons/<application>/<action>.png`, fetched over
`raw.githubusercontent.com` by the icon resolver, which consults this store after an
application's own art and the local cache, and before generating anything.

## What may live here

**Only generated art.** Every image in this repository was produced by an image model from a
description of what the action does. Nothing an application ships is here, and nothing that
ships with one may be added: OrcaSlicer's icons are AGPL, Chrome's are a trademark, and both
are resolved locally on each machine instead. That rule is enforced in the tool — `store.publish`
refuses anything whose origin is not `generated` — and it is the reason this repository can be
public at all.

Generated glyphs here are released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/):
take them, fix them, redraw them.

## Uploading is opt-in

A path here names an application and an action, which says something about what the person who
uploaded it runs and what they do with it. So nothing is uploaded unless asked:

```sh
python3 -m shortcuts icons <app> --generate --publish
```

Fetching is anonymous and needs no account. `OPENDECK_ICON_STORE=0` turns the store off
entirely; `OPENDECK_ICON_REPO=owner/name` points the tool at a different one.

## Correcting a bad icon

The paths are readable rather than hashed, so a wrong or ugly glyph can be found and replaced
by anyone: open a pull request with a better 96×96 PNG at the same path. A machine that already
cached the old one clears it by deleting `~/.cache/opendeck-shortcuts/icons`.
