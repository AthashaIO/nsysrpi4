
https://hexdocs.pm/nerves/customizing-systems.html

```bash
git checkout tags/v1.20.1
#update mix.exs metadata
mix deps.get
mix local.nerves
mix nerves.system.shell
make menuconfig
#select gpm with test tools and evtest
make savedefconfig
make
exit
#create precompiled artifact
mix nerves.artifact
```
