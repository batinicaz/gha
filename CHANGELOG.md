# Changelog

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

### [1.15.2](https://github.com/batinicaz/gha/compare/v1.15.1...v1.15.2) (2026-04-13)

### [1.15.1](https://github.com/batinicaz/gha/compare/v1.15.0...v1.15.1) (2026-04-13)

## [1.15.0](https://github.com/batinicaz/gha/compare/v1.14.0...v1.15.0) (2026-04-12)


### Features

* create shared tf docs update workflow ([c570d81](https://github.com/batinicaz/gha/commit/c570d810e47511434114198560395ef334645258))

## [1.14.0](https://github.com/batinicaz/gha/compare/v1.13.8...v1.14.0) (2026-04-12)


### Features

* use terraform docks from downloaded binary ([24c520a](https://github.com/batinicaz/gha/commit/24c520a8cd9e04fec1e02f87d8ee600ae7aa6427))

### [1.13.8](https://github.com/batinicaz/gha/compare/v1.13.7...v1.13.8) (2026-04-12)


### Bug Fixes

* major tag update not working if workflow files have been modified ([e145dee](https://github.com/batinicaz/gha/commit/e145dee1756fe10cbe4ef76db2ad1f7532a30114))

### [1.13.7](https://github.com/batinicaz/gha/compare/v1.13.6...v1.13.7) (2026-04-12)

### [1.13.6](https://github.com/batinicaz/gha/compare/v1.13.5...v1.13.6) (2026-04-10)

### [1.13.5](https://github.com/batinicaz/gha/compare/v1.13.4...v1.13.5) (2026-04-10)

### [1.13.4](https://github.com/batinicaz/gha/compare/v1.13.3...v1.13.4) (2026-04-02)

### [1.13.3](https://github.com/batinicaz/gha/compare/v1.13.2...v1.13.3) (2026-03-29)


### Bug Fixes

* renovate automerge for docker deps (versioning lacks range support) ([993ef0a](https://github.com/batinicaz/gha/commit/993ef0a3f9228fe3b8e990dbd8700fc865baeb28))

### [1.13.2](https://github.com/batinicaz/gha/compare/v1.13.1...v1.13.2) (2026-03-29)


### Bug Fixes

* exclude own images from renovate minimumReleaseAge gate ([d229e0f](https://github.com/batinicaz/gha/commit/d229e0fe1a0c97f16a3c79394b5f4ad62f27c0fd))

### [1.13.1](https://github.com/batinicaz/gha/compare/v1.13.0...v1.13.1) (2026-03-29)


### Bug Fixes

* renovate delaying for internal images ([10aef06](https://github.com/batinicaz/gha/commit/10aef06f13b086b75c739ca6654b86b2bfbd3516))

## [1.13.0](https://github.com/batinicaz/gha/compare/v1.12.0...v1.13.0) (2026-03-29)


### Features

* move pre-commit to run direct on runner + improve caching ([2e1d1c0](https://github.com/batinicaz/gha/commit/2e1d1c09c5ef11b4f20a1a7f746396b5045f01b1))

## [1.12.0](https://github.com/batinicaz/gha/compare/v1.11.2...v1.12.0) (2026-03-29)


### Features

* **renovate:** do not open prs until ready to merge + skip wait for internal images ([e01957c](https://github.com/batinicaz/gha/commit/e01957c262545b5ee9d6216795d2d2cce171f7dc))

### [1.11.2](https://github.com/batinicaz/gha/compare/v1.11.1...v1.11.2) (2026-03-29)


### Bug Fixes

* add concurrency lock to terraform plan and apply jobs ([7e32b85](https://github.com/batinicaz/gha/commit/7e32b850e262f8563c909842f0b1907ba9823384))

### [1.11.1](https://github.com/batinicaz/gha/compare/v1.11.0...v1.11.1) (2026-03-29)

## [1.11.0](https://github.com/batinicaz/gha/compare/v1.10.4...v1.11.0) (2026-03-29)


### Features

* add shared renovate preset with automerge rules ([87a845d](https://github.com/batinicaz/gha/commit/87a845dabed3717a948a5df8191b6d874bdfba67))

### [1.10.4](https://github.com/batinicaz/gha/compare/v1.10.3...v1.10.4) (2026-03-29)


### Bug Fixes

* only include v1 tag on this repo ([f2f6cd0](https://github.com/batinicaz/gha/commit/f2f6cd0bc2da742ab87dae571b7a536b3e9eab93))

### [1.10.3](https://github.com/batinicaz/gha/compare/v1.10.2...v1.10.3) (2026-03-29)

### [1.10.2](https://github.com/batinicaz/gha/compare/v1.10.1...v1.10.2) (2026-03-29)


### Bug Fixes

* codeql action causing renovate lookup failures ([e38cbc6](https://github.com/batinicaz/gha/commit/e38cbc654a49ceeacd79cd16fbae1d4285e5610a))

### [1.10.1](https://github.com/batinicaz/gha/compare/v1.10.0...v1.10.1) (2026-03-29)

## [1.10.0](https://github.com/batinicaz/gha/compare/v1.9.4...v1.10.0) (2026-03-29)


### Features

* add support for extra env variables in terraform workflows ([3ef35fd](https://github.com/batinicaz/gha/commit/3ef35fdbc6d646c6120af90e67384ecd75810545))

### [1.9.4](https://github.com/batinicaz/gha/compare/v1.9.3...v1.9.4) (2026-03-24)

### [1.9.3](https://github.com/batinicaz/gha/compare/v1.9.2...v1.9.3) (2026-03-24)


### Bug Fixes

* handle strip_v=false correctly in resolve-versions ([79afb83](https://github.com/batinicaz/gha/commit/79afb83a5ce9ae149979c6ebca417e9480f6fa8a))

### [1.9.2](https://github.com/batinicaz/gha/compare/v1.9.1...v1.9.2) (2026-03-24)


### Bug Fixes

* use readarray instead of pipe-into-while in resolve-versions ([4a55159](https://github.com/batinicaz/gha/commit/4a551596d7c1f7c995bcba46ae78287efd88988f))

### [1.9.1](https://github.com/batinicaz/gha/compare/v1.9.0...v1.9.1) (2026-03-24)

## [1.9.0](https://github.com/batinicaz/gha/compare/v1.8.4...v1.9.0) (2026-03-24)


### Features

* add resolve-versions composite action ([ca972e4](https://github.com/batinicaz/gha/commit/ca972e428c65cf8f7c4ba59b4a94dbcc9c9d8deb))
* replace trivy with grype for image scanning ([5b89fd4](https://github.com/batinicaz/gha/commit/5b89fd49ab0de1b4e401521a6e62ba8fb2144e82))

### [1.8.4](https://github.com/batinicaz/gha/compare/v1.8.3...v1.8.4) (2026-03-18)

### [1.8.3](https://github.com/batinicaz/gha/compare/v1.8.2...v1.8.3) (2026-03-14)

### [1.8.2](https://github.com/batinicaz/gha/compare/v1.8.1...v1.8.2) (2026-03-13)

### [1.8.1](https://github.com/batinicaz/gha/compare/v1.8.0...v1.8.1) (2026-03-10)


### Bug Fixes

* typo no-cache-filter → no-cache-filters ([bf72b7a](https://github.com/batinicaz/gha/commit/bf72b7a37ebfcdd08d63fda21bd9debd673602c7))

## [1.8.0](https://github.com/batinicaz/gha/compare/v1.7.4...v1.8.0) (2026-03-09)


### Features

* add no_cache_filter input for stage-level cache bypass ([7b17eed](https://github.com/batinicaz/gha/commit/7b17eed3ff3019dfb59fae44ad5561ef1a529cd1))

### [1.7.4](https://github.com/batinicaz/gha/compare/v1.7.3...v1.7.4) (2026-03-09)


### Bug Fixes

* split trivy scan from SARIF report to prevent false positives ([c9f6887](https://github.com/batinicaz/gha/commit/c9f6887dbbcdc17b1c8f533442467c69cfb33cfe))

### [1.7.3](https://github.com/batinicaz/gha/compare/v1.7.2...v1.7.3) (2026-03-05)

### [1.7.2](https://github.com/batinicaz/gha/compare/v1.7.1...v1.7.2) (2026-03-04)

### [1.7.1](https://github.com/batinicaz/gha/compare/v1.7.0...v1.7.1) (2026-03-04)

## [1.7.0](https://github.com/batinicaz/gha/compare/v1.6.3...v1.7.0) (2026-03-04)


### Features

* add support for running smoke tests on built image ([4e660c0](https://github.com/batinicaz/gha/commit/4e660c0e7209a0f930e10fb5ef5d395acfc54473))

### [1.6.3](https://github.com/batinicaz/gha/compare/v1.6.2...v1.6.3) (2026-03-02)

### [1.6.2](https://github.com/batinicaz/gha/compare/v1.6.1...v1.6.2) (2026-02-25)

### [1.6.1](https://github.com/batinicaz/gha/compare/v1.6.0...v1.6.1) (2026-02-24)

## [1.6.0](https://github.com/batinicaz/gha/compare/v1.5.7...v1.6.0) (2026-02-24)


### Features

* unpin codeql due to frequent changes ([1e53971](https://github.com/batinicaz/gha/commit/1e5397110b49d3274386d001ca2629bac356ef79))

### [1.5.7](https://github.com/batinicaz/gha/compare/v1.5.6...v1.5.7) (2026-02-24)

### [1.5.6](https://github.com/batinicaz/gha/compare/v1.5.5...v1.5.6) (2026-02-24)

### [1.5.5](https://github.com/batinicaz/gha/compare/v1.5.4...v1.5.5) (2026-02-23)

### [1.5.4](https://github.com/batinicaz/gha/compare/v1.5.3...v1.5.4) (2026-02-23)

### [1.5.3](https://github.com/batinicaz/gha/compare/v1.5.2...v1.5.3) (2026-02-21)


### Bug Fixes

* include sem ver in docker tags ([4b6bb8e](https://github.com/batinicaz/gha/commit/4b6bb8e14b87527a3236c7fec544c3bac728a4f4))

### [1.5.2](https://github.com/batinicaz/gha/compare/v1.5.1...v1.5.2) (2026-02-21)


### Bug Fixes

* cache to registry instead of gha in docker builds to enable better cache reuse regardless of tag vs branch build ([c2438d8](https://github.com/batinicaz/gha/commit/c2438d8a30f8e59291833d4e7bdc9a9acd197842))

### [1.5.1](https://github.com/batinicaz/gha/compare/v1.5.0...v1.5.1) (2026-02-21)


### Bug Fixes

* allow pushing tags for docker builds ([ac49bfb](https://github.com/batinicaz/gha/commit/ac49bfba2d41019d9ffa38940f3c442dd224b987))

## [1.5.0](https://github.com/batinicaz/gha/compare/v1.4.1...v1.5.0) (2026-02-21)


### Features

* add caching support to pre-commit ([9b4aa90](https://github.com/batinicaz/gha/commit/9b4aa901267386f9551b6f759039eba3e0c314f5))

### [1.4.1](https://github.com/batinicaz/gha/compare/v1.4.0...v1.4.1) (2026-02-21)


### Bug Fixes

* pass token as secret instead of build arg ([71d1f0e](https://github.com/batinicaz/gha/commit/71d1f0e02a3ee3cbbd17026309330bfa433b7178))

## [1.4.0](https://github.com/batinicaz/gha/compare/v1.3.1...v1.4.0) (2026-02-21)


### Features

* pass github token to docker build ([af55f64](https://github.com/batinicaz/gha/commit/af55f644c820dfecaee74ce8bd164174a6e0463a))

### [1.3.1](https://github.com/batinicaz/gha/compare/v1.3.0...v1.3.1) (2026-02-21)

## [1.3.0](https://github.com/batinicaz/gha/compare/v1.2.14...v1.3.0) (2026-02-21)


### Features

* add configurable push to docker workflow + trivvy scanning ([4eb6c4e](https://github.com/batinicaz/gha/commit/4eb6c4e4c13941c29339bb33a108a4c40f31a766))

### [1.2.14](https://github.com/batinicaz/gha/compare/v1.2.13...v1.2.14) (2026-02-12)

### [1.2.13](https://github.com/batinicaz/gha/compare/v1.2.12...v1.2.13) (2026-02-11)

### [1.2.12](https://github.com/batinicaz/gha/compare/v1.2.11...v1.2.12) (2026-02-03)

### [1.2.11](https://github.com/batinicaz/gha/compare/v1.2.10...v1.2.11) (2026-01-30)

### [1.2.10](https://github.com/batinicaz/gha/compare/v1.2.9...v1.2.10) (2026-01-30)


### Bug Fixes

* move token generation action to actively maintained action ([f4a1d93](https://github.com/batinicaz/gha/commit/f4a1d9312d554c381d2b3f714ec15fdb3c570b53))

### [1.2.9](https://github.com/batinicaz/gha/compare/v1.2.8...v1.2.9) (2026-01-30)

### [1.2.8](https://github.com/batinicaz/gha/compare/v1.2.7...v1.2.8) (2026-01-30)

### [1.2.7](https://github.com/batinicaz/gha/compare/v1.2.6...v1.2.7) (2026-01-30)

### [1.2.6](https://github.com/batinicaz/gha/compare/v1.2.5...v1.2.6) (2026-01-30)

### [1.2.5](https://github.com/batinicaz/gha/compare/v1.2.4...v1.2.5) (2025-04-13)


### Bug Fixes

* token clash in docker workflow and update docs ([bdf8665](https://github.com/batinicaz/gha/commit/bdf866582e114ab8ff181d5befdd829a7f6c948c))

### [1.2.4](https://github.com/batinicaz/gha/compare/v1.2.3...v1.2.4) (2025-04-13)

### [1.2.3](https://github.com/batinicaz/gha/compare/v1.2.2...v1.2.3) (2024-11-20)

### [1.2.2](https://github.com/batinicaz/gha/compare/v1.2.1...v1.2.2) (2024-11-20)

### [1.2.1](https://github.com/batinicaz/gha/compare/v1.2.0...v1.2.1) (2023-07-12)


### Bug Fixes

* use pre-commit image from ghcr ([82bba85](https://github.com/batinicaz/gha/commit/82bba85c680c0cf8269c365360227692e65400ac))

## [1.2.0](https://github.com/batinicaz/gha/compare/v1.1.1...v1.2.0) (2023-07-12)


### Features

* add pre-commit action ([348db4f](https://github.com/batinicaz/gha/commit/348db4f1a4f1a9ba819aa3ca1174ee41b67e91df))

### [1.1.1](https://github.com/batinicaz/gha/compare/v1.1.0...v1.1.1) (2023-07-11)

## 1.1.0 (2023-07-11)


### Features

* add auto release workflow ([bb089da](https://github.com/batinicaz/gha/commit/bb089da54b86f8fe361b9941cf958a13c5bb92a9))


### Bug Fixes

* move workflows to top level as GHA does not support custom directory structure ([b6d17f9](https://github.com/batinicaz/gha/commit/b6d17f9d497e1dbfd0b1f26a41226a6c8ddf1c0b))
* negate condition so release runs when NOT triggered by a bot ([c2215cc](https://github.com/batinicaz/gha/commit/c2215cc6dbf9434484afe9f0d5044fb552a2b9cf))
* optional params for release workflow were required ([e8969f8](https://github.com/batinicaz/gha/commit/e8969f8c650d3c9e978227d5204cac8c08c72c0b))
* quote commiter name/email to avoid line break issues ([20057fa](https://github.com/batinicaz/gha/commit/20057faa09324ab90e3750de42615129085ce554))
* typo in release workflow input --> inputs ([cc24c71](https://github.com/batinicaz/gha/commit/cc24c71c8afa12a2d3576e44db35028e36a4409b))
