# selas

An interactive 2D visualization workbench for Pandas DataFrames, built with [Panel](https://panel.holoviz.org/) and [HoloViews](https://holoviews.org/). It supports scatter, hexbin, and datashader views.

This project is managed with [uv](https://docs.astral.sh/uv/).

## Installation

With uv (recommended):

```bash
uv add selas
```

With pip:

```bash
pip install selas
```

After installation, the CLI entry is available as `explore`.

## Development (uv)

```bash
uv sync
uv run python -c "import selas; print(selas.__all__)"
```

Project layout uses `src/`:

```text
src/selas/
```

## Quick Start

```python
import pandas as pd
from selas import launch_explorer

# Load your data
df = pd.read_csv("your_data.csv")

# Launch the explorer
dashboard = launch_explorer(df)
dashboard.show(port=5006)
```

## CLI (FITS)

Launch directly from a FITS table file:

```bash
explore data.fits
```

Optional arguments:

```bash
explore data.fits --title "Cluster Explorer" --port 5006
```

## Architecture

The package is organized into specialized modules:

- `explorer.py`: Main orchestration and public API
- `colormap.py`: Colormap configuration and utilities
- `data.py`: DataFrame preparation and column selection
- `scatter_renderer.py`: Scatter plot rendering and color mapping
- `hexbin_renderer.py`: Hexbin plot rendering
- `datashader_renderer.py`: Datashader-based rendering for large datasets
- `ui.py`: Widget creation, callbacks, and layout assembly

## License

MIT License
