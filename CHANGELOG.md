# Changelog

All notable changes to avocado-bsp-imx8mp-evk are documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.1]

### Changed
- Kernel-specific packages moved under `kernel-6.6.*` / `kernel-6.18.*` blocks
  so one extension installs on both the 2024 and 2026 feeds: the per-chip
  88W8997 firmware and `kernel-module-crct10dif-ce` stay on 6.6; 6.18 takes
  `firmware-nxp-wifi-all-{sdio,pcie}` instead (meta-imx 6.18.20 drops the
  per-chip packages, and crct10dif is no longer a module).
- 6.18: mainline `mwifiex` modules and `firmware-nxp-wifi-8997` for the EVK's
  stock 88W8997 M.2 module, which NXP's 6.18 driver and firmware dropped.

## [0.1.0]

### Added
- Initial release: Board support for the i.MX 8M Plus EVK.
- CI via the shared `avocado-linux/actions` reusable workflows: PR build check
  (`test.yml`) and tag-driven package + publish to the Avocado feed (`release.yml`).
