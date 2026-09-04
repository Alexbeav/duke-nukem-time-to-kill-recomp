# Development log

## 2026-09-01 — setup executable-name parity

The public `v0.3.0` source used different CMake and setup-relaunch executable
names. The corrected source uses `Duke_Nukem__Time_to_Kill_Recompiled` in all three title-owned paths.
`Test-SetupExecutableNameParity.ps1` passes. Exact-ZIP automatic relaunch is
still required before release.

## 2026-09-04 — Linux setup tool instructions

A Bazzite user reported that the Linux first-run setup showed a checked
**Download latest portable toolchain** option, but selecting **Next** only
showed a native-tools error. The exact `v0.3.5` source confirmed the mismatch:
the POSIX host requires native CMake, Ninja, Python 3, and C/C++ compilers, but
the shared UI and generated setup guide still described the Windows portable
pack.

The local correction pins `recomp-ui` `be8ac1d03ee19d55394b5a5f2d9d1506edd56659`
and `psxrecomp` `c5206ac2f8498576706606c3e73ddaa2cc630dea`.
Linux and macOS now list the native tools and show **Check tools**. Windows
keeps the portable download and offline-zip controls. Generated setup guides
now use platform-specific instructions.

Evidence:

- Exact report: <https://www.reddit.com/r/decomps/comments/1w3rqef/alexbeavs_recomps_batch_2_26_more_ps1_titles/p7q038n/>
- Official Bazzite guidance: <https://docs.bazzite.gg/Installing_and_Managing_Software/Homebrew/>
  recommends Homebrew for command-line tools. This was treated as an install
  lead; the source fix was reproduced against the pinned launcher code.
- Homebrew formula checks: <https://formulae.brew.sh/formula/cmake>,
  <https://formulae.brew.sh/formula/ninja>, and
  <https://formulae.brew.sh/formula/llvm>.
- Windows MinGW build: all nine `recomp-ui` tests pass.
- Linux Ubuntu container build: all nine `recomp-ui` tests pass.
- Exact-title Linux setup-host build: configure passes and all 163 build steps
  link `Duke_Nukem__Time_to_Kill_Recompiled`.
- Focused package, POSIX toolchain, shell syntax, and documentation-link tests
  pass.

Corpus disposition:

- The first exact-title configure lacked the nested rewind source. This matched
  `PSX-BUILD-009`; the release checkout uses recursive submodules, and the
  pinned source restored the expected configure route.
- The nested clone then reproduced the Windows path-budget symptom in
  `PSX-WIN-008`. A short scratch leaf at the same pinned commit passed. No new
  generic finding was created.

The Ubuntu 20.04 release route also produced a local exact Linux setup ZIP.
Its host requires at most `GLIBC_2.29`; both emitters require at most
`GLIBC_2.14`. The archive guide has zero portable-pack claims, and the Linux
binary contains the native-tool copy with zero Windows portable-control
strings. No release was published. Bazzite execution remains required.
