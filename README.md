# selas

An interactive 2D visualization workbench for Pandas DataFrames, built with [Panel](https://panel.holoviz.org/) and [HoloViews](https://holoviews.org/). It supports scatter, hexbin, and datashader views.

This project is managed with [uv](https://docs.astral.sh/uv/).

## Installation

With uv (recommended):

```bash
uv add selas
```

For CLI usage without adding to a project:

```bash
uvx --from selas explore --help
```

For a globally installed CLI:

```bash
uv tool install selas
```

With pip:

```bash
pip install selas
```

After installation, the CLI entry is available as `explore`.

## Quick Start

```python
import pandas as pd
from selas import launch_explorer

# Load your data
df = pd.read_csv("your_data.csv")

# Launch and serve the explorer
launch_explorer(df, port=5006, show=True)
```

## CLI (FITS)

The CLI currently supports FITS files only for now.

Launch directly from a FITS table file:

```bash
explore data.fits
```

Optional arguments:

```bash
explore data.fits --title "Cluster Explorer" --port 5006
```

## Development (uv)

```bash
git clone https://github.com/Straw674/selas
cd selas
uv sync --extra dev
```

Useful commands:

```bash
uv run explore --help
uv run pytest
uv build
```

## Release Versioning

This repository uses Semantic Versioning with
[python-semantic-release](https://python-semantic-release.readthedocs.io/).
The next version is inferred from Conventional Commit prefixes:

- `fix:` -> patch bump
- `feat:` -> minor bump
- `feat!:` or `BREAKING CHANGE:` -> major bump

Run locally:

```bash
uv sync --extra dev
uv run semantic-release version
```

The GitHub workflow also runs this automatically on pushes to `main`.

## License

MIT License
