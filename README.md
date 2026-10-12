# iris (archived)

> **This repository is archived and read-only.** Iris now ships
> inside the Hale compiler. Development continues in
> [`hale-lang/hale`](https://github.com/hale-lang/hale), under
> [`iris/`](https://github.com/hale-lang/hale/tree/main/iris).
> Open issues and pull requests there, not here.

Iris is the realtime observer for running Hale systems. It attaches
to live processes over shared memory, fuses them into one system
graph, and renders the locus tower, message topology and transport
behavior as they happen.

## Using iris today

There is nothing to install. Iris is embedded in the `hale` binary:

```sh
hale run --observe path/to/prog.hl   # program + observer, one command
open http://127.0.0.1:8787

hale iris [port] [artifact.json]     # attach to every LOTUS_OBS=1 process
hale iris inspect <artifact.json>    # artifact-side locus inspector
```

The user guide is the Iris chapter of the Hale book:
[`docs/src/systems/iris.md`](https://github.com/hale-lang/hale/blob/main/docs/src/systems/iris.md).

## Where everything went

Everything in this repo was carried into `hale-lang/hale`. The copies
there are canonical and newer than the ones here.

| Here | In `hale-lang/hale` |
| --- | --- |
| `DESIGN.md`, `PROTOCOL.md`, `INSPECTOR.md`, `VISION-FORWARD.md` | `iris/` |
| `emitter/`, `consumer/` (incl. `fuse-hl`), `observe/`, `inspect/`, `render/web/` | `iris/` |
| `examples/` | `iris/examples/` |
| `UPSTREAM-NOTE-*.md` | `iris/` (later handoffs are in `iris/handoffs/`) |
| `verification/` (GenMC models) | `verification/` |

## What is left here

- **History.** The design and protocol history up to the fold,
  starting with the observer reframe (`b6dab57`, 2026-07-22).
- **The original spike.** The May 2026 modeling-surface prototype
  (raylib bindings, lotus_viz, heron, the pane system, an MCP server)
  is tagged [`v0.8.0`](https://github.com/hale-lang/iris/tree/v0.8.0).
  None of it carried forward.

The docs in this tree describe iris at shm protocol 0.4. They are kept
for reference only. Do not build against them.
