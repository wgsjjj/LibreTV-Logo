# LibreTV Logo

LibreTV TV 用的直播台标库。把 [mytv-android/myTVlogo](https://github.com/mytv-android/myTVlogo) 的 PNG 统一缩放到 **256px 宽、WebP q82**，按频道名直接拼地址调用。

**4027 张，34.2 MB**（原始素材 878 MB，压缩到 3.9%）

## 在 LibreTV TV 里怎么用

进「设置 → 直播 → 台标地址」，填这一行（**推荐，实测最稳**）：

```
https://ghfast.top/https://raw.githubusercontent.com/wgsjjj/LibreTV-Logo/main/img/{name}.webp
```

`{name}` 会被替换成频道名（URL 编码后）。App 内部会把 `CCTV1综合` 自动归一成 `-CCTV1`，所以不用手改文件名。

想快一点可以用 Pages（偶尔会抽）：

```
https://wgsjjj.github.io/LibreTV-Logo/img/{name}.webp
```

备用：

```
https://gh-proxy.com/https://raw.githubusercontent.com/wgsjjj/LibreTV-Logo/main/img/{name}.webp
```

三条通道实测（2026-11-06，本机，中文名交叉验证）：

| 通道 | 成功率 | 单张耗时 | 说明 |
|---|---|---|---|
| ghfast.top | 5/5 | 约 1.0s | 推荐 |
| gh-proxy.com | 5/5 | 约 2.2s | 备用 |
| GitHub Pages | 3/5 | 约 0.5s | 快但偶发连不上 |
| jsDelivr | — | — | 不可用：仓库超过代理阈值，301 跳回 raw，国内直连不通 |

需要整个库下载：`https://github.com/wgsjjj/LibreTV-Logo/archive/refs/heads/main.zip`（约 34 MB）

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
| `international-list.txt` | 未收录的 2801 个境外台标文件名，按需自行补齐 |
| `international-big.txt` | 上表中 515 个 ≥300KB 的（共 740 MB，占源库 93% 体积） |

## 覆盖范围

- **CCTV 全系列** 22 张（含 4K、8K、欧洲、美洲、5+）
- **中文台名** 3801 张：各省卫视、地方台、港澳台、专业频道（CCTV 付费系列、咪咕、DOX、求索、天元围棋等）
- **国际台** 204 张（第一批顺带拉的，不完整）

不含：境外政治宣传类频道。

## 境外台标（未收录，可自行补齐）

源库另有 **2801 张纯英文名的境外台标，共 796 MB**。其中 515 张 ≥300KB 的占了 740 MB（93% 体积），剩下 2286 张只有 56 MB。本仓库暂未收录。

| 清单 | 内容 |
|---|---|
| `international-list.txt` | 全部 2801 个文件名，一行一个 |
| `international-big.txt` | 其中 515 个 ≥300KB 的，就是体积大头 |

**下载整包（878 MB）**

```
https://github.com/mytv-android/myTVlogo/archive/refs/heads/main.zip
https://ghfast.top/https://github.com/mytv-android/myTVlogo/archive/refs/heads/main.zip
```

**按名单单张取**（`{name}` 换成清单里的名字，空格要 URL 编码成 `%20`）

```
https://ghfast.top/https://raw.githubusercontent.com/mytv-android/myTVlogo/main/img/{name}.png
```

想省流量就只下 `international-big.txt` 以外的 2286 张小图（56 MB），能覆盖 82% 的台标数量。

## 来源与版权

原始素材来自 [mytv-android/myTVlogo](https://github.com/mytv-android/myTVlogo)（AGPL-3.0）。本仓库仅做等比缩放 + WebP 转码，未改动图形本身，按 AGPL-3.0 同样开源。

台标版权归各电视台所有，此处仅用于客户端识别频道，不作商业用途。如权利人要求下架，提 issue 即可。
