# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.6.1] - 2020-07-13
### Added
- Publicly expose the `Error` type returned by `Upkeep::start`.

## [0.6.0] - 2020-07-06
This version of `quanta` was a massive overhaul of man areas of the API and internals, which was
done in a single PR: ([#19](https://github.com/metrics-rs/quanta/pull/19)).  You can read the PR
description for the finer details.  All changes below are part of the aforementioned PR.

### Changed
- `Clock::now` now returns a monotonic value in all cases.
- No longer possible to get a negative value from `Clock::delta`.
- Calibration is no longer a fixed one second loop, and will complete when it detects it has a
  statistically viable calibration ratio, or when it exceeds 200ms of wall-clock time.  In most
  cases, it should complete in under 10ms.
- Calibration is now shared amongst all `Clock` instances, running only once when the first `Clock`
  is created.

## [0.5.2] - 2020-05-01
### Changed
- Fix the logic to figure out when calibration is required. ([#14](https://github.com/metrics-rs/quanta/pull/14))

## [0.5.1] - 2020-04-11
### Changed
- Small tweak to the docs.

## [0.5.0] - 2020-04-11
### Changed
- Switch to `mach` for macOS/iOS as it was deprecated in `libc`. ([#12](https://github.com/metrics-rs/quanta/pull/12))
- Switch to `core::arch` for instrinics, and drop the feature flagged configuration to use it. ([#12](https://github.com/metrics-rs/quanta/pull/12))
- Switch to `criterion` for benchmarking. ([#12](https://github.com/metrics-rs/quanta/pull/12))

## [0.4.0] - 2020-02-20
### Changed
- Differentiate between raw and scaled time by adding a new `Instant` type. ([#10](https://github.com/metrics-rs/quanta/pull/10))

## [0.2.0] - 2019-03-10
### Changed
- Fixed support for Windows.  It was in a bad way, but actually works correctly now!
- Switched to Azure Pipelines CI + Cirrus CI, including formatting, tests, and benchmarks, for Linux, macOS, Windows, and FreeBSD.

## [0.1.0] - 2019-01-14
### Added
- Initial commit.
