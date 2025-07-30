# Torus Sampling

Helical coil distribution sampling on torus surfaces using JAX and BlackJAX nested sampling.

## Setup

In top level directory, where the pyproject is

```bash
pip install uv
uv sync
```

You may wish to bind `uv run` to a shorter command:
```bash
alias py="uv run python"
```

## Usage

Run nested sampling example:
```bash
uv run python sample_torus.py
```