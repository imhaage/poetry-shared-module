# poetry-shared-module

## Setup

3 projects created with `poetry new <project_name>`:
- 1 `shared` module
- 2 projects sharing the `shared` module: `project1` & `project2`

## Installing dependencies

The projects using the `shared` module must declare the following dependencies in the `pyproject.toml`.

```toml
[tool.poetry.dependencies]
...
shared = { path = "../shared" }
```

## Importing shared module

The `shared` module contains the `hello()` function :

```python
# shared/shared/share_module.py

def hello():
    print("From shared module !")
```

The `hello()` function is imported in `project1` and `project2` this way :

```python
# project1/project1/main.py

from shared.shared_module import hello

if __name__ == "__main__":
    hello()
```