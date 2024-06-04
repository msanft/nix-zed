# nix-zed❄️

This is an extension for the [Zed editor](https://github.com/zed-industries/zed), providing support for the [Nix language](https://github.com/NixOS/nix).

## How to install

nix-zed can be installed through Zed's extension manager. To do so, open
the command palette (Ctrl+Shift+P) in Zed and type `zed: extensions`. From there, you can search for the `Nix language` extension and install it.

## Features

- [x] Syntax highlighting
- [x] Code completion (brackets, etc.)
- [x] Language server integration (nixd)
- [ ] Language server configurability (choosing another Nix LSP, such as nil)
- [ ] Inlay hints (such as package versions)
- [ ] Intelligent hinting when "nixd" is unavailable
- [ ] JSON highlighting for `flake.lock` files

## Contributing

Contributions are welcome! If you have any ideas or suggestions, feel free to open an issue or a pull request.

## Development

To develop on this extension, you can follow the [upstream guide](https://github.com/zed-industries/extensions/blob/main/AUTHORING_EXTENSIONS.md) for authoring extensions.

On NixOS, if you want to use developer extensions in Zed, you'll need to patch the interpreter for the WASM toolchain installed by Zed:

```bash
patchelf --set-interpreter /run/current-system/sw/bin/ld.so $HOME/.local/share/zed/extensions/build/wasi-sdk/bin/wasm-ld
patchelf --set-interpreter /run/current-system/sw/bin/ld.so $HOME/.local/share/zed/extensions/build/wasi-sdk/bin/clang
```

## Related projects

There is a predecessor to this project, [zed-nix](https://github.com/hasit/zed-nix). Unfortunately, it seems to not
be actively maintained anymore.
