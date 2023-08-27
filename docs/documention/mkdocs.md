# MkDocs

## Links

- [MkDocs](https://www.mkdocs.org/)
- [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
- [MkDocs Material Reference](https://squidfunk.github.io/mkdocs-material/reference/)

## Installation

```bash
pip install mkdocs
```

I don't bother with anything else as I alwasy use a docker container for MkDocs.

## Docker Compose

```yaml title="docker-compose.yml"
version: '3.9'
services:
  primer:
    image: polinux/mkdocs
    environment:
      LIVE_RELOAD_SUPPORT: 'true'
      ADD_MODULES: 'mkdocs-git-revision-date-localized-plugin mkdocs-material pymdown-extensions pygments'
      FAST_MODE: 'true'
      DOCS_DIRECTORY: '/mkdocs'
      UPDATE_INTERVAL: 15
      AUTO_UPDATE: 'true'
    ports:
      - 8000:8000
    volumes:
      - ./:/mkdocs
```

This will mount the current directory as `/mkdocs` in the container and run MkDocs in fast mode with live reload support. The project directory must have a mkdocs.yml file in it and a docs directory with at least an index.md file in it.

## mkdocs.yml
    
```yaml title="mkdocs.yml"
site_name: Harmon's Tech Primer
theme:
  name: material
  palette:
    - scheme: slate
      primary: black
      accent: blue
      toggle:
        icon: material/brightness-4
        name: Switch to light mode
    - scheme: default
      primary: black
      accent: blue
      toggle:
        icon: material/brightness-7
        name: Switch to dark mode
  features:
    - content.code.copy
    - content.code.select
    - content.code.annotate
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
      use_pygments: true
      auto_title: false
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format

```

This file has Light and Dark mode support as well as Mermaid support. It also has code highlighting support. and Copy and Select support for code blocks.
