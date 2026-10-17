# Abyss Arch builds

Experimental PKGBUILDs and `.SRCINFO` files for all 17 Abyss repositories.
Native Arch clean-chroot builds and installation tests are **not yet validated**.
This Git repository is not an AUR publication or an official Arch repository.

`packages/` contains the native definitions, in the dependency order recorded in
`sources.json`. Each package is pinned to a source commit and SHA-256 checksum.
Package dependency names were checked against Arch's current official core/extra
repository indexes. The compositor's missing udis86 dependency is supplied as
an explicitly pinned source archive rather than an assumed official package.

Build each package with `makepkg` in a clean Arch environment. Install its built
dependencies in the next clean build environment before building dependants.
Update and check `.SRCINFO` using `makepkg --printsrcinfo` whenever editing a
PKGBUILD. The metadata files were generated with the official makepkg script using
`--printsrcinfo` in an isolated environment. Package resolution and compilation
were not run; this metadata check is not a native Arch package build.

AUR account registration is currently unavailable to the maintainer. AUR uploads
remain pending; this does not prevent using and testing the PKGBUILDs from Git.
No AUR account, upload or package adoption has been performed.

Maintainer: bb8TheRobot <bb8therobot85@gmail.com>. Packaging: 0BSD.
Upstream source licenses and notices remain applicable. The attribution audit
remains a separate release prerequisite.

License scope and the retained upstream notices are described in [LICENSES.md](LICENSES.md).
