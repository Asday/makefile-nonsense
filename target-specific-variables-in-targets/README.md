# Makefile nonsense

Part nineteen or so.

This particular bit of nonsense demonstrates using target-specific variables in target names.  This can be useful to avoid duplicating a bunch of rules just so one can build into two separate directories (perhaps with different config).

Given a directory structure like the following:

```
.
.
├── makefile
└── src
    ├── a
    └── b
```

The contained [`makefile`](makefile) "builds" the "source" into the following structure:

```
.
.
├── c
│   ├── a
│   └── b
├── d
│   ├── a
│   └── b
├── makefile
└── src
    ├── a
    └── b
```

Where one can imagine `c/` is a release configured build, and `d/` is a debug configured build.  The sky's the limit.

Intermediary targets to build not-quite-everything are named `all-$(base)` where `$(base)` is present in `$(bases)`.
