# Setup Godot Action

This GitHub Action sets up the Godot Engine from the official GitHub releases for Linux, macOS, or Windows. It automatically downloads, extracts, and makes the Godot binary available in your workflow.

## Inputs

- `version`: Godot version (e.g. `4.4.1-stable`). **Required**
- `platform`: Platform string (e.g. `linux.x86_64`, `macos.universal`, `win64.exe`). **Required**

## Outputs

- Sets the `GODOT4` environment variable to the path of the Godot binary.
- Adds the binary's directory to the `PATH`.

## Example Usage

```yaml
- name: Setup Godot
  uses: your-org/setup-godot-action@v1
  with:
    version: '4.4.1-stable'
    platform: 'linux.x86_64'

- name: Check Godot version
  run: |
    $GODOT4 --version
```
