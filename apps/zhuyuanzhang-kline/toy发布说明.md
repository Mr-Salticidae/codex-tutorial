# 朱元璋K线人生 · B站 Toy 发布说明

本应用为**单文件自包含** HTML（全内联 CSS/JS，无外链、无绝对路径、无 history 路由），可直接作为 B站 Toy 上传。

## 包信息

| 项 | 值 |
| --- | --- |
| 入口 | `apps/zhuyuanzhang-kline/index.html`（单文件，62KB） |
| 建议 slug | `zhu-yuanzhang-kline`（发布后不可改，更新时保留） |
| 封面 | `toy封面_1200x900.png`（1200×900，4:3，真实成品帧） |
| 手机端 | 已适配（viewport 齐备，`<520/640/980px` 响应式断点） |
| 内容预检 | toy_doctor 通过：`{ "ok": true, "findings": [] }` |
| Toy 项目 id | **待发布后回填** ← 更新全靠它，首发成功后立刻记这里 |

## 发布步骤（需交互，作者本人完成）

```bash
# 1. 装 CLI（Windows PowerShell，官方脚本）
irm https://boss.hdslb.com/toy-cli/toy/install.ps1 | iex

# 2. 登录（走浏览器 B站 OAuth）
toy login

# 3. 预览（不提交审核，只生成 preview_url）
toy create apps/zhuyuanzhang-kline/index.html \
  --title "朱元璋K线人生" --slug zhu-yuanzhang-kline \
  --poster apps/zhuyuanzhang-kline/toy封面_1200x900.png --json

# 4. 浏览器打开 preview_url 核对无误后，同参数加 --yes 提交审核
#    提交成功返回 {id, status}，把 id 回填到上表
```

> 指向 `index.html`**文件本身**打包，封面 png 与本说明不会被打进上传包。
> 更新走 `toy update <id> apps/zhuyuanzhang-kline/index.html ...`，**保留原 slug**，别删了重建。
> 发布≠立即可见：提交后进审核（审核中/已发布/未通过/超时），过审约 10 分钟。
> 分享用 `https://www.bilibili.com/toy/zhu-yuanzhang-kline/index.html`（带 index.html）。
