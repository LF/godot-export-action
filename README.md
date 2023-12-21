# Godot export action

Exports a Godot project.

## Usage

```yaml
name: my-workflow

on: push

jobs:
  export:
    runs-on: ubuntu-latest
    container: lfdev/godot-headless:latest
    steps:
      - uses: LF/godot-setup-action@v1
      - uses: LF/godot-export-action@v1
        with:
          path: ./export/my-project.exe
          target: Windows Desktop
```

While the image [lfdev/godot-headless](https://hub.docker.com/r/lfdev/godot-headless) from Docker Hub is used in this example, this action should work in environments where `godot` is installed in the runner's PATH.

This example also uses [LF/godot-setup-action](https://github.com/LF/godot-setup-action) to make sure support files are accessible by the runner. If your runner environment handles setting up support files in a different way, you can omit or change that step.
