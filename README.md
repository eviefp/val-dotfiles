# nixosConfigurations

## Installing

```sh
sudo nixos-rebuild switch --flake .#default
```

## Updating nixpkgs

```sh
nix flake update
```

## Upgrading to a different nixpkgs version

Edit `flake.nix`' `input.nixpkgs` to refer to the new version, e.g.

```nix
    # ...
    nixpkgs.url = "github:nixos/nixpkgs?ref=nixos-25.04";
```
or
```nix
    # ...
    nixpkgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
```

## Optional: building the nixosConfiguration without switching to it

```sh
nix build .#nixosConfigurations.default.config.system.build.toplevel
```
