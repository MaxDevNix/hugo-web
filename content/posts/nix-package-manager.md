+++
title = "Nix Package Manager"
date = "2025-03-17T07:58:35+01:00"
tags = ["Linux", "PackageManager", "Nix", "Errors Fixes", ]
draft = true
+++

<!--This is a package manager with one of the largest repositories
(80 000+ packages), that can be installed on most distros.-->

This is a standalone package manager,
that, by default, is bundled with NixOS.
I learned about it from ChrisTitusTech's
[YouTube](https://youtube.com/watch?v=Ty8C2B910EI) and
[Vlog](https://christitus.com/nix-package-manager)
It has one of the largest [repositories](https://github.com/nixos/nixpkgs)
([120 000+ packages](https://repology.org/repository/nix_unstable))
that has both free and open-source as well as proprietary software
that is pretty up to date.

## Installation
Sources:
- Official Website:
    - https://nixos.org/download
    - https://nix.dev/install-nix
- GitHub Repository: https://github.com/NixOS/nix

```
curl -L https://nixos.org/nix/install | sh
```

Arch Linux (Pacman)
``` pacman -Sy nix```

### Verify Installation
Check if installation was successful by opening a terminal and typing:
```
nix --version
```
Output should be
```
nix (Nix) {version X.Y.Z}
```

## Installing of packages from nix repository
<!-- https://stop-using-nix-env.privatevoid.net/ -->

### Trying packages before installing them
<!-- https://nix.dev/tutorials/first-steps/ad-hoc-shell-environments.html -->
Nix package manager has a nice feature, that allows

## Help
- Official Website
    - https://nixos.org/
    - https://nix.dev/
- Github
    - https://github.com/NixOS/
- Reddit
    - https://reddit.com/r/Nix/
    - https://reddit.com/r/NixOS/
- ManPages
    - nix
    - nix-env
    - nix-store
    - nix-shell
    - nix-channel

### Command Cheatsheet
- Base Command: nix-env
    - ``` -i , --install {package} ``` 
    - ``` -iA, --install --attrib nixpkgs.{package} ```

### Troubleshooting:

#### Error: Programs not showing up in start menu
NIX stores all .desktop files (icons for apps used by the start menu) in
/home/$USER/.nix-profile/share/applications, but start menus usually read from
/home/$USER/.local/share/applications.

#### Solution
Make symlinks in /home/$USER/.local/share/applications pointing to
/home/$USER/.nix-profile/share/applications
```
ls -s /home/$USER/.nix-profile/share/applications/* /home/$USER/.local/share/applications/ 
```

If that doesn't work, copy the files from /home/$USER/.nix-profile/share/applications
to /home/$USER/.local/share/applications
```
cp -v /home/$USER/.nix-profile/share/applications/* /home/$USER/.local/share/applications 
```

Another method you can try, is adding $HOME/.nix-profile/share to $XDG_DATA_DIRS like this
```
export XDG_DATA_DIRS=$HOME/.nix-profile/share:$XDG_DATA_DIRS
```


#### Error: unable to build profile. There is a conflict for the following files:

#### Solution:
There is no solution, as far as i have found, that would reliably do that. 
If you have found something, please post it as a pull request updating this file
on (git{page})[https://git{page}/{user}/{repo}/content/posts/nix-package-manager
with an accompanying sources and photos/video of the successful operation (recommended).

#### Error: profile '{profile path}' is incompatible with 'nix-env': please use 'nix profile' instead

#### Solution
There is no solution, as far as i have found, that would reliably do that. 
If you have found something, please post it as a pull request updating this file
on (git{page})[https://git{page}/{user}/{repo}/content/posts/nix-package-manager
with an accompanying sources and photos/video of the successful operation (recommended).


#### Error: when installing ghostty with `nix-env -iA nixpkgs.ghostty` or `nix profile install ghostty` or `nix profile install nixpkgs#ghostty` ...

### Uninstalling Nix Package Manager
