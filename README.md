# manjaro-juno-tablet
Manjaro drivers for Juno Tablet

A ```SWAP partition``` (not file) is required to be created when installing Manjaro, otherwise suspend-to-hibernate will not work.

## Compile Manually

```sudo pacman -S make```

```makepkg -si```

## Install from Manjaro's Repo

```sudo pacman -S juno-tablet```

## Kernel 6.1
Requires ```kernel 6.1``` otherwise sound will not work after ```Hibernate```.

```sudo pacman -S linux61```

####################

<a href="https://junocomputers.com">https://junocomputers.com</a>
