## Release notes

**v0.7.0** (2026-01-11)

- Now hosted on Github
- `upgrade` now explicitly uses the A binary for version tests. This
  fixes a logic hole which would have resulted in the B binary getting
  clobbered if the `upgrade` command was run while it was active


**v0.6.0** (2026-01-07)

- Added `unsetup` command to cleanly remove FBM
- Small QoL improvements


**v0.5.3** (2025-12-22)

- Fix for a spurious error message on self-update
- Require root only when modifying filesystem
- More informative `status` output
- Env check now silent except on error


**v0.5.0** (2025-12-11)

- FAH version check no longer touches disk
- `status` command fixes
- More documentation


**v0.4.0** (2025-12-10)

- Script self-updating enabled
- Parameterized URLs
- Small fixups and tweaks
- Improved documentation
- Add `sha512sum` as a prerequisite


**v0.3.1**

- Groundwork for self-update
- Small fixes


**v0.3.0**

- Lower FAH bandwidth usage by using the beta releases metadata file
  instead of downloading a release tarball
- Switch to A/B nomenclature
- Retain B binary when active
- Add `jq` as a prerequisite


**v0.2.0**

- Initial internal testing version

