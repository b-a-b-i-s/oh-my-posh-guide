# Oh My Posh Guide

## Oh My Posh

- [Oh My Posh Website :globe_with_meridians:](https://ohmyposh.dev/)
- [Oh My Posh Github](https://github.com/jandedobbeleer/oh-my-posh)

## Installation

Instructions: <https://ohmyposh.dev/docs/installation/windows>

Or simply type

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

## Configure Powershell

`notepad $PROFILE` (Create new file with `New-Item -Path $PROFILE -Type File -Force` if not prompted to create)

Add the following line to the file

```txt
oh-my-posh init pwsh | Invoke-Expression
```

To use a custom theme type the following line instead:

```txt
oh-my-posh init pwsh --config $env:POSH_THEMES_PATH\thecyberden.omp.json | Invoke-Expression
```

All themes available at: <https://ohmyposh.dev/docs/themes>

I have customized the thecyberden with some extra stuff in [.thecyberden-babis.omp.json](./.thecyberden-babis.omp.json). You can download it and add a link to it as shown above.

## Use nerd font to show icons

Download Meslo font: <https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/Meslo.zip>

Extract and install `Meslo LG M Regular Nerd Font Complete Mono Windows Compatible.ttf` or/and `Meslo LG S Regular Nerd Font Complete Mono Windows Compatible.ttf`. I prefer small but Medium is also needed for correct sizing in IntelliJ.

## Use in Windows Terminal

MesloLGM NF for Medium / MesloLGS NF for Small

![terminal](https://user-images.githubusercontent.com/63171080/182594596-00ee51d9-6668-4b56-aa29-348553a93a67.png)

## Use in IntelliJ

File > Settings > Editor > Font > Typography Settings > Fallback font > MesloLGM NF

## Use in bash

You can use this in wsl or Linux by adding the following to your `~/.bashrc` and `/root/.profile`.

```bash
eval "$(oh-my-posh init bash --config ~/<mytheme>.omp.json)"
```

Inside the WSL, you can find your Windows user's home folder here: `/mnt/c/Users/<WINDOWSUSERNAME>`.

## Note

Sadly icons aren't shown in Powershell app by itself because installed fonts aren't detected in Powershell settings. This can be fixed by editing registry as found [here](https://github.com/andreberg/Meslo-Font/wiki/Using-Meslo-LG-with-the-Windows-Console) or [here](https://www.softwareok.com/?seite=faq-PowerShell&faq=3) or [here](https://superuser.com/questions/502340/how-can-i-install-a-new-font-in-powershell-console) which isn't available in company laptops. After a registry change even with just one font addition (or none at all ?) all installed fonts even if not listed in registry will probably show up in Powershell settings.
<!-- However registry can be changed by creating a .reg file, converting it to .exe and running as Thycotic. -->
