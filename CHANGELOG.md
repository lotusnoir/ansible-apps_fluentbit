# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.1](https://github.com/lotusnoir/ansible-apps_fluentbit/compare/1.2.0...1.2.1) - 2025-11-29

### Commits

- add no changes on run flag to keep idempotence [`767818e`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/767818ec231c200092d0599c97c8ba90bdd02803)

## [1.2.0](https://github.com/lotusnoir/ansible-apps_fluentbit/compare/1.1.0...1.2.0) - 2025-11-27

### Commits

- update main to include success flag at the end to be able to monitor last playbook run [`ba2c670`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/ba2c670f2372e81d422412b08e45557b3102f374)

## [1.1.0](https://github.com/lotusnoir/ansible-apps_fluentbit/compare/1.0.0...1.1.0) - 2025-11-06

### Commits

- add oraclelinux10 support + lint and core fixes [`e892f8c`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/e892f8ce125e482bce0c84578e2d3b201f950136)

## [1.0.0](https://github.com/lotusnoir/ansible-apps_fluentbit/compare/0.3.0...1.0.0) - 2025-10-29

### Commits

- add trixie (debian13) support [`94e5240`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/94e5240d15c8cc2b68ff183351c6d20dd7bb6848)
- update core, molecule + gitlab-ci [`1d2516c`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/1d2516c713de6e428da9c69e5f436db79a7cbe1c)
- fix molecule paralelism and little updates [`2289a3e`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/2289a3ebc0e409c0e2f53b6cedfbfad5a28ddbd0)
- fix vars [`da7073b`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/da7073bed954256cc815172be269b9e7985fafec)
- changes on molecule + split tasks on different files [`1e46dd2`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/1e46dd2ca97ac9736b01a9079d695e9351b1bdbf)
- changes on molecule [`7b0e28a`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/7b0e28a2de011d20909544c5732f09483ab2550b)
- add opt nobest on repo for redhat as new versions fails [`0808236`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/08082360f2f063db9c67503d1218099ec6bfb196)
- add feature to wite log as adm user instead of root [`8aba940`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/8aba940b3268e2f9b3068130678aae12667cdb5d)
- add LimitNOFILE in systemd file as too may open file occurs in some distribs [`6e6b708`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/6e6b70829a3cb673bd0fa3b6ef3917071bf17e72)
- fix lint [`6fe7a03`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/6fe7a039147ed427b79000f44c6d7175b2f5e1ce)

## [0.2.0](https://github.com/lotusnoir/ansible-apps_fluentbit/compare/0.1.0...0.2.0) - 2025-02-28

### Commits

- fix molecule paralelism and little updates [`fb0888d`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/fb0888d2e8495973a24c23ed6fa59c3e4219367b)
- add support for ubuntu24 [`5a26af0`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/5a26af0b429c709ab4c563be5bac34be94feab54)
- add version on molecule play image to maintain support on old release [`e77e8fa`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/e77e8fa29425e594f97af542049c2f5471b85a01)
- remove support for debian10 / ubuntu18 / redhat8 [`5bf2b84`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/5bf2b84ac1d48e1148a9360098f1b00f7fe94a8b)
- add retry on get_url key [`1e1d7a0`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/1e1d7a09858728c99d95e9d0f33ea4d65e310afe)
- update molecule [`4ba6a9a`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/4ba6a9aa4dbf2f316ead08e605770d029185dfc1)
- fix idempotence [`68c59a5`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/68c59a5e78c784b25f34530605b810aa4a6fec87)
- add redhat 9 to default supported distrib [`0cdd998`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/0cdd99887ad5986b58b0adebbdb312cbe8b73353)
- fix redhat8 repo [`03eea69`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/03eea69f65f077b8c4077a89d5afe736b4231f89)
- add redhat8 support [`17b0262`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/17b0262b39e3f0397fb095ba4b7c6ecf6d1d6037)

## 0.1.0 - 2021-12-10

### Commits

- fix: temporary remove molecule tests the time to fix them [`89747ac`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/89747acec6be4e41b2224ecd4ca09c2106dd632a)
- fix molecule + lint [`75663f5`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/75663f5a6b7028e9a9f0556267ec21ddaa292fab)
- add clean task [`c03ec6c`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/c03ec6cc211c83567c3cd662d55357a27d344dd5)
- update vars + molecule [`44d2748`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/44d27487de73cc2c080e905671cb1c0f9fae1307)
- add vars and fixes [`a886f7d`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/a886f7d8ec866fc55eab16a76addff4436b3618c)
- fix default path [`a09cfad`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/a09cfad595f4e9794e41978934c81c8e0e986b07)
- fix yamllint [`ad83c72`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/ad83c72d830f5e12258555f922b885c0e072b95c)
- update meta [`df5c149`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/df5c14916430d59f4440f417fa2e5a4e0ea561b2)
- initial commit [`86ad125`](https://github.com/lotusnoir/ansible-apps_fluentbit/commit/86ad125308c7bb7357d2490b1cf17eaeccf0315c)
