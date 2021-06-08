# Changelog

## 0.2.0 2021-06-08

- added support for ansible-core 2.11
- added support for ansible 3.0.0 and 4.0.0

## 0.1.2 2021-04-02

- CI: install system ansible
- CI: use playbook from mafalb.ansible to install molecule

## 0.1.1 2021-03-30

- CI for alma 8
- CI is ansible-lint 5 ready

## 0.1.0 2021-02-19

- configure squid via squid_cfg dictionary
- CI Testing on RHELish and Debianish Systems
- improvements to CI

## 0.0.3 2020-12-07

### Changed

- added CHANGELOG

### Changed in CI

- use actions/checkout@v2
- use default working-dir in run steps
- test against ansible 2.10 and ansible 2.9
- run github actions CI on Ubuntu 20.04
- fix internal network definition in molecule
- do not force molecule 3.0.4 anymore

### Removed
