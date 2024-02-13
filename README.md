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
These are configuration files which have a `.conf` file extension and are located in `/etc/systemd/resolved.conf.d`. They contain one or multiple configuration options in a single, or multiple `.conf` files.

## Drop-ins
I have created two main types of drop-ins, single drop-ins - which have a single configuration option (for fine-grained control), and complete - which contain all configuration options. All drop-ins have comments included to explain the option functions, which have been taken directly from the *resolved.conf.d* manual.

### Individual drop-ins
1. DNS config - primary DNS servers
    - Default DNS config

        [00-resolved-dns.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns.conf)
    - Cloudflare DNS config

        [00-resolved-dns-cloudflare.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns-cloudflare.conf)
    - Google DNS config

        [00-resolved-dns-google.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns-google.conf)
    - Quad9 DNS config

        [00-resolved-dns-quad9.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns-quad9.conf)
1. Fallback DNS config - fallback to secondary DNS servers when primary DNS servers can't be reached
    - Default DNS fallback config

        [00-resolved-dns_fallback.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_fallback.conf)
    - Cloudflare DNS fallback config

        [00-resolved-dns_fallback-cloudflare.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_fallback-cloudflare.conf)
    - Google DNS fallback config

        [00-resolved-dns_fallback-google.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_fallback-google.conf)
    - Quad9 DNS fallback config

        [00-resolved-dns_fallback-quad9.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_fallback-quad9.conf)
1. DNSSEC - toggle DNSSEC (secure DNS) for DNS resolution

    [00-resolved-dnssec.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dnssec.conf)
1. DNS over TLS - toggle DNS over TLS (provide DNS over TLS secure protocol) for DNS resolution

    [00-resolved-dns_over_tls.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_over_tls.conf)
1. DNS Stub Listener - toggle DNS Stub Listener

    [00-resolved-dns_stub_listener.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_stub_listener.conf)
1. DNS Stub Listener Extra - add optional additional IPv4, IPv6, protocol, port number(s) for the DNS resolver to listen on

    [00-resolved-dns_stub_listener_extra.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_stub_listener_extra.conf)
1. Cache - toggle DNS caching to speed up DNS resolution

    [00-resolved-cache.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-cache.conf)
1. Cache from Localhost - toggle DNS Stub Listener

    [00-resolved-cache_from_localhost.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-cache_from_localhost.conf)
1. Domains - configure search domains

    [00-resolved-domains.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-domains.conf)
1. LLMNR (Link-Local Multicast Name Resolution) - toggle DNS Stub Listener

    [00-resolved-dns_stub_listener.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_stub_listener.conf)
1. Multicast DNS - Controls Link-Local Multicast Name Resolution support (RFC 4795[1]) on the local host

    [00-resolved-dns_multicast.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-dns_multicast.conf)
1. Read Etc Hosts - toggle whether or not the DNS resolver reads hosts from `/etc/hosts`

    [00-resolved-read_etc_hosts.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-read_etc_hosts.conf)

1. Resolve Unicast Single Label - configure whether or not the DNS resolver resolves A and AAAA queries for single-label names over classic DNS

    [00-resolved-resolve_unicast_single_label.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-resolve_unicast_single_label.conf)

1. Stable Retention Sec - set the maximum time DNS records are cached for

    [00-resolved-stable_retention_sec.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/individual/00-resolved-stable_retention_sec.conf)

### Complete drop-ins
1. Default - complete DNS resolver configuration with resolved defaults

    [00-resolved.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/full/00-resolved.conf)
1. Cloudflare - complete DNS resolver configuration with resolved defaults, includes Cloudflare DNS and Fallback DNS servers

    [00-resolved-cloudflare.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/full/00-resolved-cloudflare.conf)
1. Google - complete DNS resolver configuration with resolved defaults, includes Google DNS and Fallback DNS servers

    [00-resolved-quad9.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/full/00-resolved-quad9.conf)
1. Quad9 - complete DNS resolver configuration with resolved defaults, includes Quad9 DNS and Fallback DNS servers

    [00-resolved-cloudflare.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/full/00-resolved-cloudflare.conf)

### Combined drop-ins
1. Default DNS & Fallback DNS - only contains DNS and fallback DNS configuration with resolved defaults

    [00-resolved-dns-fallback_dns.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-dns-fallback_dns.conf)
2. Cloudflare DNS & Fallback DNS - only contains DNS and fallback DNS configuration for Cloudflare's DNS servers

    [00-resolved-dns-fallback_dns-cloudflare.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-dns-fallback_dns-cloudflare.conf)
3. Google DNS & Fallback DNS - only contains DNS and fallback DNS configuration for Google's DNS servers

    [00-resolved-dns-fallback_dns-google.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-dns-fallback_dns-google.conf)
4. Quad9 DNS & Fallback DNS - only contains DNS and fallback DNS configuration for Quad9's DNS servers

    [00-resolved-dns-fallback_dns-quad9.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-dns-fallback_dns-quad9.conf)

5. No DNS - complete DNS resolver configuration without DNS and fallback DNS configuration.

    [00-resolved-no_dns.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-no_dns.conf)

1. DNS Stub Listener & DNS Stub Listener Extra - only contains the DNS stub listener & DNS stub listener extra configuration options.

    [00-resolved-dns_stub_listener-dns_stub_listener_extra.conf](https://github.com/schmittyd/resolved.conf.d/blob/main/combined/00-resolved-dns_stub_listener-dns_stub_listener_extra.conf)

## Usage

There a several ways these drop-ins can be used. First of all, the `00` at the start of the filename is the priority of the drop-in - `00` is the highest priority.

### Examples:

  1. `00-resolved-dns-fallback_dns.conf`, `00-resolved-dns-fallback_dns-cloudflare.conf`, `00-resolved-dns-fallback_dns-google.conf` *or* `00-resolved-dns-fallback_dns-quad9.conf`

      Default DNS & Fallback DNS, Cloudflare DNS & Fallback DNS, Google DNS & Fallback DNS *or* Quad9 DNS & Fallback DNS. Priority is not important, as only one DNS service is being used and no other configuration is required. The Default configuration can be used if you are using different DNS servers, such as those provided by your ISP.

  1. `00-resolved.conf`, `00-resolved-cloudflare.conf`, `00-resolved-google.conf` *or* `00-resolved-quad9.conf`

      Default, Cloudflare, Google *or* Quad9 full configuration, if other options are required to be configured. Priority is not important, as only one DNS service is being used. The Default configuration can be used if you are using different DNS servers, such as those provided by your ISP.

  1. `00-resolved-dns-fallback_dns-cloudflare.conf` *and* `00-resolved-no_dns.conf`

      Cloudflare DNS & Fallback DNS *and* No DNS config. Priority is not important, as this is essentially the same as using `00-resolved-cloudflare.conf`.

  1. `00-resolved-dns-fallback_dns-cloudflare.conf`, `00-resolved-no_dns.conf` *and* `01-resolved-dns-fallback_dns-google.conf`

      Cloudflare DNS & Fallback DNS, No DNS config *and* Google DNS & Fallback DNS. Priority is important, as Cloudflare's DNS & Fallback DNS servers and No DNS are given highest priority and Google's DNS & Fallback DNS servers are used as a backup if Cloudflare's DNS servers are unavailable for resolution. All other configuration is *shared* between the Cloudflare and Google DNS configurations. This is for advanced use, if additional configuration is required for *both* DNS services.

  1. `00-resolved-cloudflare.conf` *and* `01-resolved-google.conf`

      Cloudflare DNS & Fallback DNS *and* Google DNS & Fallback DNS. Priority is important, as Cloudflare's DNS & Fallback DNS servers and other configuration are given highest priority, and Google's DNS & Fallback DNS servers and other configuration are used as a backup if Cloudflare's DNS servers are unavailable for resolution. All other configuration is specific to each DNS configuration. This is for advanced use, if additional configuration is required for *each* DNS service.

  1. `00-resolved-dns-fallback_dns.conf`, `00-resolved-dns-fallback_dns-cloudflare.conf`, `00-resolved-dns-fallback_dns-google.conf` *or* `00-resolved-dns-fallback_dns-quad9.conf` *and* any other *individual* drop-in

      Default DNS & Fallback DNS, Cloudflare DNS & Fallback DNS, Google DNS & Fallback DNS *or* Quad9 DNS & Fallback DNS *and* any other *individual* drop-in. Priority is not important, as only one DNS service is being used and no other configuration is required. The Default configuration can be used if you are using different DNS servers, such as those provided by your ISP. Other *individual* drop-ins can be used with the same priority, if you only require certain options. This is for advanced use, if additional configuration is required for the chosen DNS service.

  1. `00-resolved-dns-fallback_dns-cloudflare.conf` *and* other *individual* drop-ins, *and* `01-resolved-dns-fallback_dns-google.conf`

      Cloudflare DNS & Fallback DNS *and* other *individual* drop-ins *and* Google DNS & Fallback DNS. Priority is important, as Cloudflare's DNS & Fallback DNS servers and No DNS are given highest priority and Google's DNS & Fallback DNS servers are used as a backup if Cloudflare's DNS servers are unavailable for resolution. All other configuration is *shared* between the Cloudflare and Google DNS configurations. Other *individual* drop-ins can be used with the same priority as `00-resolved-dns-fallback_dns-cloudflare.conf`, if you only require certain options for *that* service. This is for advanced use, if additional configuration is required for the *highest priority* (primary) DNS service.

  1. `00-resolved-dns-fallback_dns-cloudflare.conf` *and* `01-resolved-dns-fallback_dns-google.conf` *and* other *individual* drop-ins

      Cloudflare DNS & Fallback DNS *and* Google DNS & Fallback DNS *and* other *individual* drop-ins. Priority is important, as Cloudflare's DNS & Fallback DNS servers and No DNS are given highest priority and Google's DNS & Fallback DNS servers are used as a backup if Cloudflare's DNS servers are unavailable for resolution. All other configuration is *shared* between the Cloudflare and Google DNS configurations. Other *individual* drop-ins can be used with the same priority as `01-resolved-dns-fallback_dns-google.conf`, if you only require certain options for *that* service. This is for advanced use, if additional configuration is required for the secondary DNS service.

  1. `00-resolved-dns-fallback_dns-cloudflare.conf` *and* other *individual* drop-ins *and* `01-resolved-dns-fallback_dns-google.conf` *and* other *individual* drop-ins

      Cloudflare DNS & Fallback DNS *and* Google DNS & Fallback DNS *and* other *individual* drop-ins. Priority is important, as Cloudflare's DNS & Fallback DNS servers and No DNS are given highest priority and Google's DNS & Fallback DNS servers are used as a backup if Cloudflare's DNS servers are unavailable for resolution. All other configuration is *dependent* on which drop-ins you use for each service. Other *individual* drop-ins *should* be used with the same priority as `00-resolved-dns-fallback_dns-cloudflare.conf` and/or `01-resolved-dns-fallback_dns-google.conf`, if you only require certain options for *each* service. This is for advanced use, if additional configuration is required for *each* DNS service.


## Installing

### Create directory to clone repository to:

`mkdir -v ~/git` or `sudo mkdir -v ~/git` *if required*

### Install Git (if not already installed):

`apt install git` or `sudo apt install git` *if required*

### Clone repository:

`git clone https://github.com/schmittyd/resolved.conf.d.git` or `sudo git clone https://github.com/schmittyd/resolved.conf.d.git` *if required*

### Copy required config to /etc/systemd/resolved.conf.d:

#### Basic single DNS service

`cd ~/git/resolved.conf.d/combined`

Select a configuration to use
  - `00-resolved-dns-fallback_dns.conf` - additional configuration is required
  - `00-resolved-dns-fallback_dns-cloudflare.conf`
  - `00-resolved-dns-fallback_dns-google.conf`
  - `00-resolved-dns-fallback_dns-quad9.conf`

Example using Cloudflare's DNS & Fallback DNS servers

`cp -v 00-resolved-dns-fallback_dns-cloudflare.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns-cloudflare.conf`

or

`sudo cp -v 00-resolved-dns-fallback_dns-cloudflare.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns-cloudflare.conf` *if required*


Restart DNS Resolver service

`sudo systemctl restart systemd-resolved`

Ping google.com to test DNS resolution

`ping -c 3 google.com`

If DNS Resolution is working, you should see similar results

    PING google.com (142.250.70.142) 56(84) bytes of data.
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=1 ttl=59 time=14.5 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=2 ttl=59 time=15.2 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=3 ttl=59 time=14.5 ms

    --- google.com ping statistics ---
    3 packets transmitted, 3 received, 0% packet loss, time 2002ms
    rtt min/avg/max/mdev = 14.480/14.720/15.185/0.328 ms
:memo: **Note:** All other DNS resolver options will be set to resolved defaults

#### Basic two DNS service using priorty

`cd ~/git/resolved.conf.d/combined`

Select two configurations to use
  - `00-resolved-dns-fallback_dns.conf` - additional configuration is required
  - `00-resolved-dns-fallback_dns-cloudflare.conf`
  - `00-resolved-dns-fallback_dns-google.conf`
  - `00-resolved-dns-fallback_dns-quad9.conf`

Example using Cloudflare's DNS & Fallback DNS servers as highest priorty and Google's DNS & Fallback DNS servers as a lower priority

`cp -v 00-resolved-dns-fallback_dns-cloudflare.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns-cloudflare.conf && cp -v 00-resolved-dns-fallback_dns-google.conf /etc/systemd/resolved.conf.d/01-resolved-dns-fallback_dns-google.conf`

or

`sudo cp -v 00-resolved-dns-fallback_dns-cloudflare.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns-cloudflare.conf && sudo cp -v 00-resolved-dns-fallback_dns-google.conf /etc/systemd/resolved.conf.d/01-resolved-dns-fallback_dns-google.conf` *if required*

Restart DNS Resolver service

`sudo systemctl restart systemd-resolved`

Ping google.com to test DNS resolution

`ping -c 3 google.com`

If DNS Resolution is working, you should see similar results

    PING google.com (142.250.70.142) 56(84) bytes of data.
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=1 ttl=59 time=14.5 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=2 ttl=59 time=15.2 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=3 ttl=59 time=14.5 ms

    --- google.com ping statistics ---
    3 packets transmitted, 3 received, 0% packet loss, time 2002ms
    rtt min/avg/max/mdev = 14.480/14.720/15.185/0.328 ms

:memo: **Note:** All other DNS resolver options will be set to resolved defaults

#### Using /etc/systemd/resolved.conf.d/combined/00-resolved-dns-fallback_dns.conf, /etc/systemd/resolved.conf.d/individual/00-resolved-dns.conf, and /etc/systemd/resolved.conf.d/individual/00-resolved-dns_fallback.conf

:memo: **Note:** For this configuration you need primary and secondary DNS IP addresses from either your ISP, or DNS services like OpenDNS. For this example OpenDNS will be used - Primary: 208.67.222.222 Secondary: 208.67.220.220

`cp -v 00-resolved-dns-fallback_dns.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns.conf`

or

`sudo cp -v 00-resolved-dns-fallback_dns.conf /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns.conf` *if required*

Edit /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns.conf

`sudo nano /etc/systemd/resolved.conf.d/00-resolved-dns-fallback_dns.conf`

    # DNS

    # Some examples of DNS servers which may be used for DNS= and FallbackDNS=:
    # Cloudflare: 1.1.1.1#cloudflare-dns.com 1.0.0.1#cloudflare-dns.com 2606:4700:4700::1111#cloudflare-dns.com 2606:4700:4700::1001#cloudflare-dns.com
    # Google:   8.8.8.8#dns.google 8.8.4.4#dns.google 2001:4860:4860::8888#dns.google 2001:4860:4860::8844#dns.google
    # Quad9:   9.9.9.9#dns.quad9.net 149.112.112.112#dns.quad9.net 2620:fe::fe#dns.quad9.net 2620:fe::9#dns.quad9.net

    # Default: 

    DNS=



    # FALLBACK DNS

    # Some examples of DNS servers which may be used for DNS= and FallbackDNS=:
    # Cloudflare: 1.1.1.1#cloudflare-dns.com 1.0.0.1#cloudflare-dns.com 2606:4700:4700::1111#cloudflare-dns.com 2606:4700:4700::1001#cloudflare-dns.com
    # Google:   8.8.8.8#dns.google 8.8.4.4#dns.google 2001:4860:4860::8888#dns.google 2001:4860:4860::8844#dns.google
    # Quad9:   9.9.9.9#dns.quad9.net 149.112.112.112#dns.quad9.net 2620:fe::fe#dns.quad9.net 2620:fe::9#dns.quad9.net

    # Default: 

    FallbackDNS=

  Add primary IP address to DNS option

    DNS=208.67.222.222

  Add secondary IP address to FallbackDNS option

    FallbackDNS=208.67.220.220

  The configuration should look like this

    # DNS

    # Some examples of DNS servers which may be used for DNS= and FallbackDNS=:
    # Cloudflare: 1.1.1.1#cloudflare-dns.com 1.0.0.1#cloudflare-dns.com 2606:4700:4700::1111#cloudflare-dns.com 2606:4700:4700::1001#cloudflare-dns.com
    # Google:   8.8.8.8#dns.google 8.8.4.4#dns.google 2001:4860:4860::8888#dns.google 2001:4860:4860::8844#dns.google
    # Quad9:   9.9.9.9#dns.quad9.net 149.112.112.112#dns.quad9.net 2620:fe::fe#dns.quad9.net 2620:fe::9#dns.quad9.net

    # Default: 

    DNS=208.67.222.222



    # FALLBACK DNS

    # Some examples of DNS servers which may be used for DNS= and FallbackDNS=:
    # Cloudflare: 1.1.1.1#cloudflare-dns.com 1.0.0.1#cloudflare-dns.com 2606:4700:4700::1111#cloudflare-dns.com 2606:4700:4700::1001#cloudflare-dns.com
    # Google:   8.8.8.8#dns.google 8.8.4.4#dns.google 2001:4860:4860::8888#dns.google 2001:4860:4860::8844#dns.google
    # Quad9:   9.9.9.9#dns.quad9.net 149.112.112.112#dns.quad9.net 2620:fe::fe#dns.quad9.net 2620:fe::9#dns.quad9.net

    # Default: 

    FallbackDNS=208.67.220.220

Press `CTRL+X` to close, Press `Y` to save then press `ENTER` to confirm overwriting the existing file.

Restart DNS Resolver service

`sudo systemctl restart systemd-resolved`

Ping google.com to test DNS resolution

`ping -c 3 google.com`

If DNS Resolution is working, you should see similar results

    PING google.com (142.250.70.142) 56(84) bytes of data.
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=1 ttl=59 time=14.5 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=2 ttl=59 time=15.2 ms
    64 bytes from mel04s01-in-f14.1e100.net (142.250.70.142): icmp_seq=3 ttl=59 time=14.5 ms

    --- google.com ping statistics ---
    3 packets transmitted, 3 received, 0% packet loss, time 2002ms
    rtt min/avg/max/mdev = 14.480/14.720/15.185/0.328 ms

:memo: **Note:** All other DNS resolver options will be set to resolved defaults
