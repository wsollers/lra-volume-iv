# lra-volume-iv

**Volume IV: Mathematical Spaces** — Overleaf-ready standalone repository.

## Structure

```text
volume-iv.tex          — full-volume root (Overleaf main document)
volume-iv-<book>.tex   — individual book roots
common/               — shared LaTeX infrastructure supplied by lra-common; ignored here
bibliography/         — per-book bibliography shards
volume-iv/             — all LaTeX content for this volume
```

## Overleaf

Upload or checkout `common/` beside this repository's TeX roots, then set the main document to `volume-iv.tex` for the full volume or to one of the book roots:

```text
volume-iv-mathematical-spaces.tex
```

`common/` is ignored by git in this volume repo; edit shared infrastructure in `lra-common`.

## Building locally

```powershell
python F:\repos\lra-governance\tools\governance\build_volume_docker.py --root F:\repos\lra-volume-iv --common-root F:\repos\lra-common
```
