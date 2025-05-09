![GitHub License](https://img.shields.io/github/license/universonic/openwrt-mihomo?style=for-the-badge&logo=github) ![GitHub Tag](https://img.shields.io/github/v/release/universonic/openwrt-mihomo?style=for-the-badge&logo=github) ![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/universonic/openwrt-mihomo/total?style=for-the-badge&logo=github) ![GitHub Repo stars](https://img.shields.io/github/stars/universonic/openwrt-mihomo?style=for-the-badge&logo=github) [![Telegram](https://img.shields.io/badge/Contact-Telegram-26A5E4?style=for-the-badge&logo=telegram)](https://t.me/mihomotproxy)

# MihomoTProxy

Transparent Proxy with Mihomo on OpenWrt.

## Prerequisites

- OpenWrt >= 23.05
- Linux Kernel >= 5.10
- firewall4

## Feature

- Transparent Proxy (TPROXY/TUN, IPv4 and/or IPv6)
- Access Control
- Profile Mixin
- Profile Editor
- Scheduled Restart

## Install & Update

### A. Install From Feed (Recommended)

1. Add Feed

```shell
# only needs to be run once
curl -s -L https://github.com/universonic/openwrt-mihomo/raw/refs/heads/main/feed.sh | ash
```

2. Install

```shell
# you can install from shell or `Software` menu in LuCI
# for opkg
opkg install mihomo
opkg install luci-app-mihomo
opkg install luci-i18n-mihomo-zh-cn
# for apk
apk add --allow-untrusted mihomo
apk add --allow-untrusted luci-app-mihomo
apk add --allow-untrusted luci-i18n-mihomo-zh-cn
```

### B. Install From Release

```shell
curl -s -L https://github.com/universonic/openwrt-mihomo/raw/refs/heads/main/install.sh | ash
```

## Uninstall & Reset

```shell
curl -s -L https://github.com/universonic/openwrt-mihomo/raw/refs/heads/main/uninstall.sh | ash
```

## How To Use

See [Wiki](https://github.com/universonic/openwrt-mihomo/wiki)

## How does it work

1. Mixin and Update profile.
2. Run mihomo.
3. Run hijack prepare script.
4. Set router hijack.
5. Set lan hijack with access control.
6. Set scheduled restart.

Note that the steps above may change base on config.

## Compilation

```shell
# add feed
echo "src-git mihomo https://github.com/universonic/openwrt-mihomo.git;main" >> "feeds.conf.default"
# update & install feeds
./scripts/feeds update -a
./scripts/feeds install -a
# make package
make package/luci-app-mihomo/compile
```

The ipk/apk file will be found under `bin/packages/your_architecture/mihomo`.

## Dependencies

- ca-bundle
- curl
- yq
- firewall4
- ip-full
- kmod-inet-diag
- kmod-nft-tproxy
- kmod-tun

## Contributors

[![Contributors](https://contrib.rocks/image?repo=universonic/openwrt-mihomo)](https://github.com/universonic/openwrt-mihomo/graphs/contributors)

## Special Thanks

- [@ApoisL](https://github.com/vernlau)
- [@xishang0128](https://github.com/xishang0128)
