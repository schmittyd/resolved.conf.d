# Linux Systemd DNS Resolver Drop-ins
[![schmittyd - resolved.conf.d](https://img.shields.io/static/v1?label=schmittyd&message=resolved.conf.d&color=black&logo=github)](https://github.com/schmittyd/resolved.conf.d "Go to GitHub repo")
[![stars - resolved.conf.d](https://img.shields.io/github/stars/schmittyd/resolved.conf.d?style=social)](https://github.com/schmittyd/resolved.conf.d)
[![forks - resolved.conf.d](https://img.shields.io/github/forks/schmittyd/resolved.conf.d?style=social)](https://github.com/schmittyd/resolved.conf.d)
[![GitHub tag](https://img.shields.io/github/tag/schmittyd/resolved.conf.d?include_prereleases=&sort=semver&color=black)](https://github.com/schmittyd/resolved.conf.d/releases/)
[![issues - resolved.conf.d](https://img.shields.io/github/issues/schmittyd/resolved.conf.d)](https://github.com/schmittyd/resolved.conf.d/issues)


## About
After spending hours googling how to fix the symbolic link for `/etc/resolv.conf` regularly resetting to `/run/systemd/resolve/stub-resolv.conf` and finding out that this is default behavior, and use to drop-ins rather than edit `/etc/resolv.conf`, I decide to create these drop-ins.


## What is the Systemd DNS Resolver?
This is a network component which handles Domain Name System (DNS) resolution, which resolves domain names (web site top-level address eg. example.com) between the host system (your system) and the upstream DNS server (the servers which are responsible for hosting domain names). Without this link you are unable to access the internet.


## What are Drop-ins?
These are configuration files which have a `.conf` file extension and are located in `/etc/systemd/resolved.conf.d`. They contain one or multiple configuration options in a single or multiple `.conf` files.

## Drop-ins
I have created two main types of drop-ins, single drop-ins - which have a single configuration option (for fine-grained control), and complete - which contain all configuration options. All drop-ins have comments included to explain the option functions, which have been taken directly from the *resolved.conf.d* manual.

### Single drop-ins
1. e
   - e
   - e
   - e
   - e
3. e
  - e
  - e
  - e
  - e
4. e
5. e
6. e
7. e
8. e
9. e
10. e
11. e
12. e

### Complete drop-ins
1. e
2. e
3. e
4. e
