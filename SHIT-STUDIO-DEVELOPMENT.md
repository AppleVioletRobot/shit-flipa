# Shit Studio Development

A small set of rules for making deliberately limited creative software without accidentally making the apps share a brain.

## The Shit Software principle

**DICK ABOUT & DISCOVER.**

The software should be simple enough to invite play, limited enough to create accidents, and functional enough that the shit parts are productive rather than merely broken.

Before adding a feature, ask whether the goal can already be achieved with the current setup. Protect the dicking about from feature creep.

## App independence

Every Shit Studio app is its own arena.

- Separate repository.
- Separate deployed app / PWA identity.
- Separate service-worker cache.
- Separate browser storage key.
- Separate export filenames where appropriate.
- An app may borrow an idea from a sibling, but it should not depend on the sibling's runtime state or controls.

**Naming rule:** storage and cache names are app-specific from birth.

```text
shit-krita-autosave
shit-flipa-autosave

shit-krita-v…
shit-flipa-v…
```

Do not use generic inherited names such as `alice-studio-autosave`.

## Forking a sibling

A fork is only the branch point. Copying the files does **not** make the new app independent.

After forking:

1. Change app name, title, splash, icon and manifest.
2. Give it its own storage key and export filenames.
3. Give it its own service-worker cache name.
4. Remove sibling-only controls and runtime code together.
5. Check for orphaned DOM references after removing controls.
6. Check for old variables/functions that no longer exist.
7. Bump asset/service-worker versions so the deployed app actually fetches the changes.
8. Test drawing/input **before** declaring the patient alive.
9. Test that changing or clearing one sibling does not affect another.

## ACKs must tell the truth

A visual ACK means exactly what it appears to mean.

A green tick for a button press means **the tap registered** unless the app can genuinely verify that the operation completed. Never imply that a file was saved when only the download action was triggered.

## Deliberate defects

Do not automatically fix limitations that create useful play.

Examples include clunky turning, arena-specific canvas sizes, and other constraints that make the medium behave like itself. Distinguish a productive limitation from a bug that prevents the basic action.

**Shitegrity:** preserve the useful shit.

## Source control

Known-working behaviour is an asset.

Before architectural surgery, establish a safe branch point. When a working mechanism has been painfully established, do not casually rewrite it while fixing something unrelated.

👹 **SOURCE CONTROL.**

## Current siblings

### Shit Krita

Tiny drawing/collage studio.

Storage: `shit-krita-autosave`

### Shit Flipa

Tiny frame-by-frame animation studio.

Storage: `shit-flipa-autosave`

Motto: **MOVE IT MOVE IT**

---

This document should grow from actual Shit Studio mistakes and discoveries rather than becoming a speculative software constitution.
