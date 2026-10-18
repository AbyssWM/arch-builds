<div align="center">

<img src="https://github.com/AbyssWM.png?size=200" width="140" alt="Abyss logo">

# 🏹 Abyss for Arch Linux

**PKGBUILDs for the complete Abyss Wayland ecosystem.**

[![Arch Linux](https://img.shields.io/badge/arch-x86__64-1793d1?style=flat-square&logo=archlinux&logoColor=white)](https://archlinux.org/) [![Packages](https://img.shields.io/badge/packages-17-7c3aed?style=flat-square)](#-packages) [![Packaging license](https://img.shields.io/badge/packaging-0BSD-blue?style=flat-square)](LICENSE)

[🌐 Website](https://abysswm.github.io/) · [📖 Install guide](https://abysswm.github.io/wiki/getting-started) · [🌊 Abyss on GitHub](https://github.com/AbyssWM)

</div>

---

> [!WARNING]
> **Experimental, pre-1.0.** Packages build natively, but no session or hardware tests have been done yet.

## 🚀 Install

Build and install the compositor with all Abyss libraries it needs — in dependency order:

```sh
git clone https://github.com/AbyssWM/arch-builds.git
cd arch-builds/packages
for p in abyssutils abyss-scanner abyssland-protocols abyssparse abysswire abyssgraphics abyssal abysstoolkit abysscursor abyssland; do
  (cd "$p" && makepkg -si --noconfirm) || break
done
```

Want the extra tools too? Run the same loop with `abyss-guiutils xdg-desktop-portal-abyss abysspicker abyssdusk abysspaper abysslock abysspolkit`.

Then pick **Abyssland** in your display manager, or run `start-abyssland` from a TTY.

> [!NOTE]
> Not on the AUR yet — AUR registration is currently closed. Until then, build straight from this repository.

## 🔨 Editing a PKGBUILD

Every package is pinned to an exact upstream commit and SHA-256 checksum (`sources.json`). After changing a `PKGBUILD`, regenerate its metadata:

```sh
makepkg --printsrcinfo > .SRCINFO
```

<details>
<summary>How the packages were verified</summary>

- All 17 packages were built with `makepkg` in the official `archlinux-bootstrap` image (signature and SHA-256 verified) and installed in dependency order.
- `.SRCINFO` regenerated with `makepkg --printsrcinfo` — identical for all 17.
- `udis86` is not in the official repos, so `abyssland` bundles a pinned udis86 source archive.
- Not yet done: test suites (`--nocheck`), runtime / session tests.

</details>

## 📋 Packages

Listed in build order — every package only depends on the ones above it.

| # | Package | Source |
|---|---|---|
| 1 | [`abyssutils`](packages/abyssutils/PKGBUILD) | [Abyssutils](https://github.com/AbyssWM/Abyssutils) |
| 2 | [`abyss-scanner`](packages/abyss-scanner/PKGBUILD) | [Abyss-scanner](https://github.com/AbyssWM/Abyss-scanner) |
| 3 | [`abyssland-protocols`](packages/abyssland-protocols/PKGBUILD) | [Abyssland-protocols](https://github.com/AbyssWM/Abyssland-protocols) |
| 4 | [`abyssparse`](packages/abyssparse/PKGBUILD) | [Abyssparse](https://github.com/AbyssWM/Abyssparse) |
| 5 | [`abysswire`](packages/abysswire/PKGBUILD) | [Abysswire](https://github.com/AbyssWM/Abysswire) |
| 6 | [`abyssgraphics`](packages/abyssgraphics/PKGBUILD) | [Abyssgraphics](https://github.com/AbyssWM/Abyssgraphics) |
| 7 | [`abyssal`](packages/abyssal/PKGBUILD) | [Abyssal](https://github.com/AbyssWM/Abyssal) |
| 8 | [`abysstoolkit`](packages/abysstoolkit/PKGBUILD) | [Abysstoolkit](https://github.com/AbyssWM/Abysstoolkit) |
| 9 | [`abysscursor`](packages/abysscursor/PKGBUILD) | [Abysscursor](https://github.com/AbyssWM/Abysscursor) |
| 10 | [`abyssland`](packages/abyssland/PKGBUILD) | [Abyssland](https://github.com/AbyssWM/Abyssland) |
| 11 | [`abyss-guiutils`](packages/abyss-guiutils/PKGBUILD) | [Abyss-guiutils](https://github.com/AbyssWM/Abyss-guiutils) |
| 12 | [`xdg-desktop-portal-abyss`](packages/xdg-desktop-portal-abyss/PKGBUILD) | [Xdg-desktop-portal-abyss](https://github.com/AbyssWM/Xdg-desktop-portal-abyss) |
| 13 | [`abysspicker`](packages/abysspicker/PKGBUILD) | [AbyssPicker](https://github.com/AbyssWM/AbyssPicker) |
| 14 | [`abyssdusk`](packages/abyssdusk/PKGBUILD) | [AbyssDusk](https://github.com/AbyssWM/AbyssDusk) |
| 15 | [`abysspaper`](packages/abysspaper/PKGBUILD) | [AbyssPaper](https://github.com/AbyssWM/AbyssPaper) |
| 16 | [`abysslock`](packages/abysslock/PKGBUILD) | [AbyssLock](https://github.com/AbyssWM/AbyssLock) |
| 17 | [`abysspolkit`](packages/abysspolkit/PKGBUILD) | [AbyssPolkit](https://github.com/AbyssWM/AbyssPolkit) |

## ⚖️ License

The packaging in this repository is **0BSD** ([LICENSE](LICENSE)). The packaged software keeps its own licenses — see [LICENSES.md](LICENSES.md).

Maintainer: bb8TheRobot &lt;bb8therobot85@gmail.com&gt;
