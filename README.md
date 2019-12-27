# Domain Rules Generator for Engintron

## Description
This script generate custom rules for hosted domains so that domains accessed via Cloudflare or hosts file are working with Engintron

## Why
[Engintron & CloudFlare](https://engintron.com/docs/#/pages/Engintron-&-CloudFlare)

[Engintron & the "Custom Rules" file (for Nginx)](https://engintron.com/docs/#/pages/Engintron-&-the-%22Custom-Rules%22-file-(for-Nginx))

## Features
- can be run as cron
- regenerates rules only if virtualhost is added/modified/deleted
- does not overwrite custom rules therefore can be used with your own custom rules

## Usage
```
Usage:
        engintron-domain-rules [option]
Options:
                -h|--help|help      : show this message
                gen|generate        : generate rules and apply
                fogen|forcegenerate : the same even if no hosts were added/deleted/changed recently
                dryrun              : display generated rules that will be applied, but do not apply
                show                : show currently applied rules
                install             : install cron
                remove|uninstall    : remove cron and previously generated rules
```

## Installation
```
cd /usr/local/bin/ && curl -skLo engintron-domain-rules https://github.com/zhubanRuban/engintron-domain-rules/raw/master/engintron-domain-rules && chmod +x engintron-domain-rules && cd -
```
Setup cron (optional):
```
engintron-domain-rules install
```
## Uninstallation
```
engintron-domain-rules remove && rm -f /usr/local/bin/engintron-domain-rules
```
