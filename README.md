# Kali — IPTV 直播源 / 点播源

全网公开源聚合，**每条直播线路都经过真实 HTTP 拉流校验**，并附带实测码率。
生成于 2026-10-09 23:45。

## 文件说明

| 文件 | 内容 |
| --- | --- |
| [`FX.json`](FX.json) | ★ TVBox 单仓配置（点播采集接口 + 直播源），推送到「仓库/线路推送」用这个 |
| [`README.md`](README.md) | 本文件 |
| [`live.m3u`](live.m3u) | 直播源全量（频道名带 [码率] 标注） |
| [`live.txt`](live.txt) | 直播源 TXT 版（频道名,地址 + #genre# 分组） |
| [`live_clean.m3u`](live_clean.m3u) | 直播源全量·干净频道名（推荐给电视，码率另见 speed_report.txt） |
| [`live_clean_jx.m3u`](live_clean_jx.m3u) | 直播源精选·干净频道名（每分类限量，推荐） |
| [`live_full.m3u`](live_full.m3u) | 直播源全量（带码率标注） |
| [`speed_report.txt`](speed_report.txt) | 全量版实测码率报告 |
| [`speed_report_jx.txt`](speed_report_jx.txt) | 精选版实测码率报告 |
| [`vod.m3u`](vod.m3u) | 点播源清单（采集接口/影视列表/TVBox 配置，给人看的清单） |

## 访问路径

**Raw 直链**（网页可打开、播放器可读取）：

```
https://raw.githubusercontent.com/296585628/Kali/main/<文件名>
```

**历史教训：`raw.githubusercontent.com` 在国内经常连不上**，如果电视上加载失败，
换下面任意一个镜像（把 `<文件名>` 替换掉即可）：

```
https://ghproxy.net/https://raw.githubusercontent.com/296585628/Kali/main/<文件名>
https://gh-proxy.com/https://raw.githubusercontent.com/296585628/Kali/main/<文件名>
https://ghfast.top/https://raw.githubusercontent.com/296585628/Kali/main/<文件名>
https://cdn.jsdelivr.net/gh/296585628/Kali@main/<文件名>
```

⚠️ **jsDelivr 对超过 20MB 的文件有限制，且大文件容易连接被重置**。实测
`FX.json`、`DT.txt` 走 jsDelivr 没问题，但 `live_full.m3u` / `ZB_ALL.txt`（1.4MB）
建议用 ghproxy / ghfast。

## 在 TVBox 上怎么用

TVBox 按**扩展名**判断文件类型：

- `*.txt` / `*.m3u` / `*.m3u8` → 当成**直播源**
- `*.json` → 当成**配置**（读取 `sites[].api`）

所以：

1. **直播源**：用「直播源推送」，地址填
   `https://ghfast.top/https://raw.githubusercontent.com/296585628/Kali/main/ZB_JX.txt`
   或 `live_clean_jx.m3u`
2. **点播源**：用「仓库/线路推送」，地址填
   `https://raw.githubusercontent.com/296585628/Kali/main/FX.json`
   （**必须是 .json**，填 DT.txt 是没用的，TVBox 会当成直播列表解析）

## EPG 节目单

```
https://epg.pw/xmltv/epg_CN.xml.gz
```

## 实测数据

- 去重后探测 13864 个地址，真实可拉流 6914 个
- 每条线路带实测码率，同频道快的排前面
- 分类：央视 119 条｜卫视 230 条｜地方/特色 3534 条｜港澳台 15 条｜海外 3016 条

> 可用性是从中国电信/联通网络出口实测的。海外源在国内宽带上大多拉不动，
> 港澳台/海外那几组请以实际播放为准；同频道有多条线路，卡了换下一条。

## 免责声明

所有地址均来自互联网公开分享，本仓库只做抓取、去重、可用性探测与整理，
不存储、不转码、不分发任何音视频内容，版权归各原始权利人所有。
仅供个人学习与网络调试使用，请勿用于商业用途。如有侵权请联系删除。
