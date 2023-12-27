# Godot CI/CD

Workflows for exporting and pushing Godot Engine projects to itch.io.

## Usage

**Example `.github/workflows/export-and-push.yml`**
```yaml
name: Export and push

on: push

jobs:

  export-and-push-windows:
    name: Windows
    uses: parsenoire/godot-ci/.github/workflows/export-and-push-windows.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:windows
      version: "3.5.3"

  export-and-push-macos:
    name: macOS
    uses: parsenoire/godot-ci/.github/workflows/export-and-push-macos.yml@v1
    secrets: inherit
    with:
      name: My Project
      target: user/my-project:macos
      version: "3.5.3"

  export-and-push-linux:
    name: Linux
    uses: parsenoire/godot-ci/.github/workflows/export-and-push-linux.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:linux
      version: "3.5.3"

  export-and-push-web:
    name: Web
    uses: parsenoire/godot-ci/.github/workflows/export-and-push-web.yml@v1
    secrets: inherit
    with:
      name: my-project
      target: user/my-project:web
      version: "3.5.3"
```

These workflows use the following actions:

- [parsenoire/butler-login-action](https://github.com/parsenoire/butler-login-action)
- [parsenoire/butler-push-action](https://github.com/parsenoire/butler-push-action)
- [parsenoire/godot-export-action](https://github.com/parsenoire/godot-export-action)
- [parsenoire/godot-setup-action](https://github.com/parsenoire/godot-setup-action)

and use these images from GitHub Container Registry:

- [ghcr.io/parsenoire/godot-headless](https://ghcr.io/parsenoire/godot-headless) ([repo](https://github.com/parsenoire/docker-godot-headless))
- [ghcr.io/parsenoire/butler](https://ghcr.io/parsenoire/butler) ([repo](https://github.com/parsenoire/docker-butler))
