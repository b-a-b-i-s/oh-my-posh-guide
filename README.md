# Oh My Posh Guide

## Oh My Posh

- [Oh My Posh Website :globe_with_meridians:](https://ohmyposh.dev/)
- [Oh My Posh Github](https://github.com/jandedobbeleer/oh-my-posh)

## Installation

### Windows

  Instructions: <https://ohmyposh.dev/docs/installation/windows>

  Or simply type

  ```powershell
  winget install JanDeDobbeleer.OhMyPosh -s winget
  ```

### macOS

  Instructions: <https://ohmyposh.dev/docs/installation/macos>

  Or simply type

  ```powershell
  brew install jandedobbeleer/oh-my-posh/oh-my-posh
  ```

### Linux

  Instructions: <https://ohmyposh.dev/docs/installation/linux>

## Configure Powershell

`notepad $PROFILE.CurrentUserAllHosts` (Create new file with `New-Item -Path $PROFILE.CurrentUserAllHosts -Type File -Force` if not prompted to create)

Add the following line to the file

```txt
oh-my-posh init pwsh | Invoke-Expression
```

To use a custom theme type the following line instead:

```txt
oh-my-posh init pwsh --config $env:POSH_THEMES_PATH/thecyberden.omp.json | Invoke-Expression
```

All themes available at: <https://ohmyposh.dev/docs/themes>

I have customized the theme called thecyberden with some extra stuff in [.thecyberden-babis.omp.json](./.thecyberden-babis.omp.json). You can download it, add it to your user folder and add a link to it as shown bellow.

```pwsh
if ($ENV:USERPROFILE) {
  oh-my-posh init pwsh --config $ENV:USERPROFILE/.thecyberden-babis.omp.json | Invoke-Expression
}
else {
  oh-my-posh init pwsh --config ~/.thecyberden-babis.omp.json | Invoke-Expression
}
```

## Use nerd font to show icons

Oh My Posh was designed to use Nerd Fonts. Nerd Fonts are popular fonts that are patched to include icons. [Website](https://www.nerdfonts.com/) | [Github](https://github.com/ryanoasis/nerd-fonts)

You can use any nerd font. I recommend Meslo or Caskaydia Cove.

Download Meslo font (Patched Apple's Menlo font, recommended by oh-my-posh): <https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/Meslo.zip>

Extract and install `Meslo LG M Regular Nerd Font Complete Mono Windows Compatible.ttf` or/and `Meslo LG S Regular Nerd Font Complete Mono Windows Compatible.ttf`. I prefer small but Medium is also needed for correct sizing in IntelliJ.

For Open Weather Maps segment (for my custom theme) to show correctly in Windows Terminal you can use [Caskaydia Cove Nerd Font Complete Mono Windows Compatible.tff](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/CascadiaCode.zip).

## Use in Windows Terminal

Settings > Defaults > Appearance > Font face > MesloLGM NF / MesloLGS NF / CaskaydiaCove NF > Save

<!-- ![terminal](https://user-images.githubusercontent.com/63171080/182594596-00ee51d9-6668-4b56-aa29-348553a93a67.png) -->

## Use in ConEmu

Settings > General > Fonts > Main console font > fontMesloLGM NF / MesloLGS NF / CaskaydiaCove NF

Settings > General > Fonts > Alternative font > fontMesloLGM NF / MesloLGS NF / CaskaydiaCove NF

## Use in IntelliJ

File > Settings > Editor > Font > Typography Settings > Fallback font > MesloLGM NF

## Use in bash

You can use this in wsl or Linux by adding the following to your `~/.bashrc` and `/root/.profile`.

```bash
eval "$(oh-my-posh init bash --config ~/<mytheme>.omp.json)"
```

Inside the WSL, you can find your Windows user's home folder here: `/mnt/c/Users/<WINDOWSUSERNAME>`.

## Use in other shells

See: <https://ohmyposh.dev/docs/installation/prompt>

## Strava

To use Strava in my custom theme connect from [here](https://ohmyposh.dev/docs/segments/strava) and edit the access_token and refresh_token in the json theme file.

## Note

Sadly icons aren't shown in Powershell app by itself because installed fonts aren't detected in Powershell settings. This can be fixed by editing registry as found [here](https://github.com/andreberg/Meslo-Font/wiki/Using-Meslo-LG-with-the-Windows-Console) or [here](https://www.softwareok.com/?seite=faq-PowerShell&faq=3) or [here](https://superuser.com/questions/502340/how-can-i-install-a-new-font-in-powershell-console) which isn't available in company laptops. After a registry change even with just one font addition (or none at all ?) all installed fonts even if not listed in registry will probably show up in Powershell settings.
<!-- However registry can be changed by creating a .reg file, converting it to .exe and running as Thycotic. -->
