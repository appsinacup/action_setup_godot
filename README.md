# Setup Godot Action

|[Website](https://appsinacup.com)|[Discord](https://discord.gg/56dMud8HYn)|
|-|-|

![example](docs/example.png)

Sets up the Godot Engine from the official GitHub releases for Linux, macOS, or Windows.

## Inputs

- `repo`: e.g. `godotengine/godot`
- `version`: e.g. `4.4.1-stable` (required)
- `release-tag`: Override in case release name is differnet from version. If empty defaults to version. (default: ``)
- `bin-path`: Path for binaries to be installed to (default: `godot-bin`)
- `download_editor`: Download the Godot Editor binary (`true`/`false`, default: `true`)
- `download_template`: Download export templates (`true`/`false`, default: `false`)
- `mono`: Download Mono version (C# support) (`true`/`false`, default: `false`)

## Outputs

- Sets the `GODOT4` environment variable to the path of the Godot binary.
- Adds the binary's directory to the `PATH`.

## Example Usage

For normal Godot Release:

```yaml
- name: Setup Godot
  uses: appsinacup/setup-godot-action@main
  with:
    version: '4.4.1-stable'

- name: Check Godot version
  run: |
    $GODOT4 --version
```

For custom Godot Release:

```yaml
- name: Setup Godot (2D Optimized)
  uses: appsinacup/setup-godot-action@main
  with:
    version: '4.4.1-stable'
    release-tag: '3d-disable'
    repo: 'appsinacup/action_godot_builder'
```
