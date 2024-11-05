Nix flake for NodeJS development
================================

To start a development shell with programs specified in flake.nix, you can clone this repository, enter the directory, and then run:

```
git clone https://github.com/wch/nix-node-demo.git
cd nix-node-demo
nix develop
```

But you don't even need to clone the repository! Instead, you can start a development shell like this:

```
# Enter development shell
nix develop github:wch/nix-node-demo
```

This development shell will have NodeJS 20 and `git` installed.

```
node -v
#> v20.17.0
```

With the above command, you'll have access to the programs specified in flake.nix, as well as any programs that are in your normal environment, like `curl`.

Alternatively, you can run in a purer environment, where only the programs specified in flake.nix are available, by using `-i`:

```
nix develop -i github:wch/nix-node-demo
```

This won't even have `curl` available, unless you modify flake.nix to include it. This mode can be useful for testing whether your flake.nix includes all the programs you need for your development environment.

