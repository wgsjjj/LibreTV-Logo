# LibreTV Logo

LibreTV TV 用的直播台标库。把 [mytv-android/myTVlogo](https://github.com/mytv-android/myTVlogo) 的 PNG 统一缩放到 **256px 宽、WebP q82**，按频道名直接拼地址调用。

**4027 张，34.2 MB**（原始素材 878 MB，压缩到 3.9%）

## 在 LibreTV TV 里怎么用

进「设置 → 直播 → 台标地址」，填这一行（**推荐，实测最快**）：

```
https://wgsjjj.github.io/LibreTV-Logo/img/{name}.webp
```

`{name}` 会被替换成频道名（URL 编码后）。App 内部会把 `CCTV1综合` 自动归一成 `-CCTV1`，所以不用手改文件名。

github.io 连不上时换这两条（同样把 `{name}` 留着）：

```
https://gh-proxy.com/https://raw.githubusercontent.com/wgsjjj/LibreTV-Logo/main/img/{name}.webp
https://ghfast.top/https://raw.githubusercontent.com/wgsjjj/LibreTV-Logo/main/img/{name}.webp
```

三条通道实测（2026-11-06，本机）：

| 通道 | 响应 | 耗时 |
|---|---|---|
| GitHub Pages | 200 | 0.64s |
| ghfast.top | 200 | 0.99s |
| gh-proxy.com | 200 | 2.17s |
| jsDelivr | 301 回源 | 不可用（仓库超过 jsDelivr 的代理阈值，会跳回 raw，国内直连不通） |

需要整个库下载的话：`https://github.com/wgsjjj/LibreTV-Logo/archive/refs/heads/main.zip`

## 命名规则

| 频道 | 文件名 | 说明 |
|---|---|---|
| 央视 | `-CCTV1.webp`、`-CCTV5+.webp` | **带前导横线** |
| 央视 4K / 8K | `-CCTV4K.webp`、`-CCTV8K.webp` | |
| 央视 4 欧洲 / 美洲 | `-CCTV4欧洲.webp`、`-CCTV4美洲.webp` | |
| 卫视、地方台、专业频道 | `湖南卫视.webp`、`北京文艺.webp`、`凤凰中文.webp` | 直接用台名 |

## 文件说明

| 文件 | 用途 |
|---|---|
| `img/` | 全部台标，4027 个 `.webp` |
| `logo-list.txt` | 一行一个台标名（不含扩展名），方便程序比对 |
| `index.json` | 带分组统计的完整清单，`groups` 里分 cctv / chinese / international |

## 覆盖范围

- **CCTV 全系列** 22 张（含 4K、8K、欧洲、美洲、5+）
- **中文台名** 3801 张：各省卫视、地方台、港澳台、专业频道（CCTV 付费系列、咪咕、DOX、求索、天元围棋等）
- **国际台** 204 张（第一批顺带拉的，不完整）

不含：境外政治宣传类频道。

## 来源与版权

原始素材来自 [mytv-android/myTVlogo](https://github.com/mytv-android/myTVlogo)（AGPL-3.0）。本仓库仅做等比缩放 + WebP 转码，未改动图形本身，按 AGPL-3.0 同样开源。

台标版权归各电视台所有，此处仅用于客户端识别频道，不作商业用途。如权利人要求下架，提 issue 即可。
