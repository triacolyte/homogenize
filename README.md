# Homogenize

## About

Homogenize is a GUI application used to extract Garry's Mod models (.gma files) and rebuild them without body groups.
It is only supported on Linux so far.

## Why?

Prop hunt doesn't allow for body groups in playermodels. This means that I need to remove them, and *homogenize* the playermodels, so to speak.

## Research

### Third Party Tools

#### Information Sources

- [GMAD][gmad-github]
- [Third Party Tools][third-party-tools-models]
- [CrowbarX][crowbarx-github]

#### GMAD

I installed gmad via their [github][gmad-github]. Their project uses `premake4`, and the build file was too outdated to work out of the box.
Instead, I just compiled the project with a single gcc command, and added header files where they were needed to compile on Linux.

I've included the modified source directory and executable in the `gmad` folder.

#### CrowbarX

I installed CrowbarX from [here][crowbar-github-release].
I also needed to install the .NET 3.1 runtime, and found installation instructions [here][dotnet-3.1-install-instructions].
I've put them below:
```
~# curl -Lo dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/e6ae53a9-8567-4f44-b6ce-684d4f4a0b27/e0c29635c1c2ae9424390a41fecc95f1/dotnet-sdk-3.1.410-linux-x64.tar.gz
~# mkdir dotnet
~# tar -C dotnet -xf dotnet.tar.gz
~# rm dotnet.tar.gz
~# export DOTNET_ROOT=~/dotnet
~# export PATH=$PATH:~/dotnet
~# dotnet --version
3.1.410
```

For testing CrowbarX on Arch Linux, I used [the AUR package][dotnet-3.1-aur], though I'll use the archive for the application, since it works universally.

### How do bodygroups work?

See [this guide][bodygroups-guide].

[gmad-github]: https://github.com/Facepunch/gmad
[third-party-tools-models]: https://developer.valvesoftware.com/wiki/Third_Party_Tools#Models
[crowbarx-github]: https://github.com/nonunknown/crowbarx
[crowbarx-github-release]: https://github.com/nonunknown/crowbarx/releases/tag/0.3
[crowbar-steam-group]: https://steamcommunity.com/groups/CrowbarTool
[dotnet-3.1-install-instructions]: https://github.com/dotnet/core/blob/main/release-notes/3.1/install-linux.md#installing-from-a-binary-archive
[dotnet-3.1-aur]: https://aur.archlinux.org/packages/dotnet-sdk-3.1-bin
[bodygroups-guide]: https://steamcommunity.com/sharedfiles/filedetails/?id=667587915
