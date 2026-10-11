# GL-MT3000 ImmortalWrt 21.02 自动构建

[![OpenWrt Builder](../../actions/workflows/build-openwrt.yml/badge.svg)](../../actions/workflows/build-openwrt.yml)
[![Update Checker](../../actions/workflows/update-checker.yml/badge.svg)](../../actions/workflows/update-checker.yml)

基于 [hanwckf/immortalwrt-mt798x](https://github.com/hanwckf/immortalwrt-mt798x)（`openwrt-21.02`），为 **GL.iNet GL-MT3000（MT7981）** 自动编译 ImmortalWrt 固件。

## 特性

- `luci-app-passwall`（最新版，sing-box + geoview，含中文）
- Docker（dockerd + dockerman）
- MTK 闭源 WiFi 驱动、HNAT / TurboACC 硬件加速、eqos-mtk QoS
- UPnP、ZeroTier、diskman、autoreboot、vlmcsd、Argon 主题、简体中文

管理地址 **192.168.3.1**，首次进入 LuCI 无密码。

## 使用

1. Fork 本仓库，在 Settings → Actions 中允许 Actions 运行
2. 创建 fine-grained PAT（权限 `Contents: Read and write`），保存为 secret `BUILD_PAT`
3. Actions → **OpenWrt Builder** → Run workflow 手动编译；**Update Checker** 每天自动检查上游更新并触发编译
4. 完成后在 **Releases** 下载固件（保留最近 3 个）

修改配置：直接改 `.config`，或用 **mt7981-config** workflow 导出解析后的配置（勾选 SSH 可进 runner 调 menuconfig）。

## 致谢

[P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt) · [hanwckf/immortalwrt-mt798x](https://github.com/hanwckf/immortalwrt-mt798x) · [ImmortalWrt](https://github.com/immortalwrt) · [Openwrt-Passwall](https://github.com/Openwrt-Passwall)

## License

[MIT](LICENSE)
