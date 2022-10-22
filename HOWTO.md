
https://hexdocs.pm/nerves/customizing-systems.html

```bash
git remote add upstream git@github.com:nerves-project/nerves_system_rpi4.git
git fetch --tags upstream
git checkout tags/v1.20.2
git checkout -b mice

#update mix.exs metadata

mix deps.get
mix local.nerves
mix nerves.system.shell

make linux-menuconfig
CONFIG_INPUT_MOUSEDEV
make linux-update-defconfig

make menuconfig
evtest
make savedefconfig

make
exit
#create precompiled artifact
mix nerves.artifact
mv *.tar.gz ~/.nerves/dl
```
