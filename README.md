<div align="center">

<img src="snap/gui/gitcomet.png" alt="GitComet logo" width="128" />

# GitComet

**A fast native desktop client for Git.**

[![gitcomet](https://snapcraft.io/gitcomet/badge.svg)](https://snapcraft.io/gitcomet)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [GitComet](https://github.com/Auto-Explore/GitComet), a native Git client with visual diffs, staging and merge conflict resolution.

</div>

---

## Getting Started

<a href="https://snapcraft.io/gitcomet"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install gitcomet
gitcomet
```

Open a repository from your home directory or launch GitComet from the application menu. Git, Git LFS, git-annex, OpenSSH and GnuPG are included.

## Configure

Manage preferences in the app. There are no `snap set` options.

| Optional access | Command |
| --- | --- |
| SSH keys and configuration in `~/.ssh` | `sudo snap connect gitcomet:ssh-keys` |
| Repositories on removable storage | `sudo snap connect gitcomet:removable-media` |

The snap has its own Git configuration. Set your identity in GitComet's built-in terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

New SSH host keys are saved in `~/snap/gitcomet/common/ssh/known_hosts`. Custom themes belong in `~/snap/gitcomet/current/.local/share/gitcomet/themes`.

## Limitations

- Host Git settings, credentials and GPG keys are not imported automatically. SSH keys require the connection above; host SSH agents and hardware tokens are not supported.
- The built-in terminal, hooks, external editors and git-annex helpers can only run programs available inside the snap. Host development toolchains are not available.
- Repositories outside your home directory or connected removable storage are restricted.
- Updates are managed by snapd.

## Build

```bash
git clone https://github.com/sidalit/gitcomet-snap.git
cd gitcomet-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/gitcomet-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/Auto-Explore/GitComet/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/gitcomet-snap/blob/main/LICENSE).
