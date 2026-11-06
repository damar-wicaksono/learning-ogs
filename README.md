# learning-ogs

Notes and worked examples from learning [OpenGeoSys](https://www.opengeosys.org/),
published as a [Jupyter Book 2](https://next.jupyterbook.org/) site.

## Setup

```bash
uv venv                  # if .venv does not exist yet
uv pip install -e .
```

Jupyter Book 2 is built on [MyST-MD](https://mystmd.org/) and downloads a bundled
Node toolchain plus the site theme on first build, so the first run needs network
access. Later builds are offline.

## Building

```bash
source .venv/bin/activate

jupyter book start                   # live-reload dev server on http://localhost:3000
jupyter book build --html            # static HTML into _build/html/
jupyter book build --html --execute  # ...re-running every notebook first
jupyter book build --html --execute --strict   # fail on any warning
```

`start` does not execute notebooks — it renders whatever outputs are saved in the
`.ipynb`. Use `--execute` when you want outputs regenerated from the code.

## Layout

| Path | Purpose |
| --- | --- |
| `myst.yml` | Project config **and** table of contents |
| `index.md` | Landing page |
| `notes/` | Markdown pages |
| `notebooks/` | Executable notebooks |
| `_build/` | Build output (gitignored) |

New pages must be added to the `toc:` block in `myst.yml` to appear in the nav.
# learning-ogs
