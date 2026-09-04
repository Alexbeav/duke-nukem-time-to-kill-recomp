# Duke Nukem: Time to Kill knowledge report

- Date: 2026-08-31
- Retail identity: USA NTSC-U `SLUS-00583`
- Architecture lane: source-only owned-input setup host
- Release target: Windows x64, Linux x64, macOS ARM64, and macOS x64; candidate version `0.3.5`
- License boundary: portfolio files use GPL-3.0-only; dependencies keep their licenses

## Current state

The operator confirmed gameplay in the private promoted package. This meets
the `bootstrap_verified` boundary. The source-only Windows package builds
locally. Exact-package setup, startup, and remote-byte gates remain open.

## Release controls

- Framework: c5206ac2f8498576706606c3e73ddaa2cc630dea
- recomp-ui: be8ac1d03ee19d55394b5a5f2d9d1506edd56659
- RetComM Studio: 249422969c1c59ac2a1f8aa2299e876a7133998e
- Distribution: owned input only
- Platform claim: pending exact-package gates on all four targets
- Deferred work: exact-package native gates and R3/R4 publication

## Open gates

1. Complete exact-package setup and a 10-second startup.
2. Run the regional and title-risk canaries from exact ZIPs.
3. Audit every downloaded private draft.
4. Bind publication authorization to the exact release manifest.

## Corpus consulted

The release work uses PSX-PUB-004, PSX-PUB-006, PSX-WIN-004,
PSX-WIN-005, PSX-WIN-006, and PSX-PUB-011.

## v0.3.3 setup correction

The source now uses `Duke_Nukem__Time_to_Kill_Recompiled` as the only setup executable name. The batch source
gate passes. The exact-ZIP automatic-relaunch canary and remote release audit
remain open. Public `v0.3.0` remains unchanged.

## v0.3.5 three-platform refresh

The source now binds the package-only privacy correction and targets Windows
x64, Linux x64, macOS ARM64, and macOS x64. The replacement build-only CI,
complete archive audit, and native package gates remain required. This source
change does not publish a release or claim platform support.

## 2026-09-04 POSIX setup instruction correction

The public Linux setup UI offered the Windows portable pack even though the
POSIX host accepts only native build tools. The corrected UI lists CMake,
Ninja, Python 3, and a C/C++ compiler, then asks the user to check those tools.
The setup package guide uses the same platform split. Windows behavior is
unchanged. Windows and Linux shared-UI builds pass all nine tests; a Bazzite
exact-package canary remains open. The exact-title Linux setup host also links
after all 163 build steps with the pinned rewind dependency. A local package
from the pinned Ubuntu 20.04 route passes its instruction, source-identity, and
glibc-floor audits. It has not run on Bazzite.
