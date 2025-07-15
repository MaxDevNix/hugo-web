+++
title = "Nix Package Manager"
date = "2025-03-17T07:58:35+01:00"
tags = ["Linux", "Package Manager", "Nix", "Errors Fixes", ]
draft = true
image = "nix.png"
featured_image = "nix.png"
+++

<!--This is a package manager with one of the largest repositories
(80 000+ packages), that can be installed on most distros.-->

[Nix](https://nixos.org) is a standalone package manager,
<!-- that, by default, is bundled with NixOS. -->
that is the default package manager for NixOS.
I learned about it from ChrisTitusTech's
[YouTube](https://youtube.com/watch?v=Ty8C2B910EI) and
[Vlog](https://christitus.com/nix-package-manager)
It has one of the largest [repositories](https://github.com/nixos/nixpkgs)
([120 000+ packages](https://repology.org/repository/nix_unstable))
that has both free and open-source as well as proprietary software
that is up to date.

## Installation
Sources:
- Official Website:
    - https://nixos.org/download
        - Multi-user install
        ```sh
        $ sh <(curl --proto '=https' --tlsv1.2 -L https://nixos.org/nix/install) --daemon
        ```
        - Single-user install
        ```sh
        $ sh <(curl --proto '=https' --tlsv1.2 -L https://nixos.org/nix/install) --no-daemon
        ```
    - https://nix.dev/install-nix
    ```sh
    $ curl -L https://nixos.org/nix/install | sh -s -- --daemon
    ```
- GitHub Repository: https://github.com/NixOS/nix
- Chris Titus Tech: https://christitus.com/nix-package-manager
```sh
$ curl -L https://nixos.org/nix/install | sh
```
Arch Linux (Pacman)
```sh
$ pacman -Sy nix
```

### Verify Installation
Check if installation was successful by opening a terminal and typing:
```sh
$ nix --version
```
Output should be
```sh
$ nix (Nix) {version X.Y.Z}
```
## Installing of packages from nix repository
<!-- https://stop-using-nix-env.privatevoid.net/ -->


### Trying packages before installing them
<!-- https://nix.dev/tutorials/first-steps/ad-hoc-shell-environments.html -->
Nix package manager has a nice feature, that allows you to try packages in an
ephemeral shell before installing them.
Try it with this command:
```sh
$ nix-shell -p {package name}
```

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
    - `-i , --install {package}` install package
    - `-iA, --install --attrib nixpkgs.{package}` install package from attribute "nixpkgs"
        [most people using nix<!--'s imperative...--> use this option, as it is faster, and less error prone](https://github.com/NixOS/nixpkgs/issues/38635#issuecomment-393657957), although it's a bit more verbose, which I don't like very much
    - `-q, --query {optional package name}` list packages installed with nix

### Troubleshooting:

#### Error: Programs not showing up in start menu/desktop
NIX stores all .desktop files (icons for apps used by the start menu) in
/home/$USER/.nix-profile/share/applications, but start menus usually read from
/home/$USER/.local/share/applications.

#### Solution
Make symlinks in /home/$USER/.local/share/applications pointing to
/home/$USER/.nix-profile/share/applications
```sh
$ ls -s /home/$USER/.nix-profile/share/applications/* /home/$USER/.local/share/applications/ 
```

If that doesn't work, copy the files from /home/$USER/.nix-profile/share/applications
to /home/$USER/.local/share/applications
```sh
$ cp -v /home/$USER/.nix-profile/share/applications/* /home/$USER/.local/share/applications 
```

Another method you can try, is adding [$HOME/.nix-profile/share to $XDG_DATA_DIRS](https://wiki.archlinux.org/title/Nix#Desktop_integration) like this
```sh
$ export XDG_DATA_DIRS=$HOME/.nix-profile/share:$XDG_DATA_DIRS
```


#### Error: unable to build profile. There is a conflict for the following files:
#### {list of files}

#### Solution:
There is no solution, as far as i have found, that would reliably do that. 
If you have found something, please post it as a pull request updating this file
on [github/maxdevnix/hugo-web](https://github.com/MaxDevNix/hugo-web/blob/main/content/posts/nix-package-manager.md)
with an accompanying sources and photos/video of the successful operation (recommended).

#### Error: profile '{profile path}' is incompatible with 'nix-env': please use 'nix profile' instead

#### Solution
There is no solution, as far as i have found, that would reliably do that. 
If you have found something, please post it as a pull request updating this file
on [github/maxdevnix/hugo-web](https://github.com/MaxDevNix/hugo-web/blob/main/content/posts/nix-package-manager.md)
with an accompanying sources and photos/video of the successful operation (recommended).


#### Error: when installing `ghostty` terminal with `nix-env -iA nixpkgs.ghostty`/`nix profile install ghostty`/`nix profile install nixpkgs#ghostty`

### Uninstalling Nix Package Manager
<!-- NUKE your OS with `sudo rm -rf /`. -->
