# 接物小游戏

移动端竖屏接物小游戏，支持本地离线运行，可打包分发给朋友直接玩耍。

## 快速开始

1. 解压压缩包到任意目录
2. 用手机或电脑浏览器打开 `index.html`
3. 点击「开始游戏」，在弹窗中选择模式（不限时 / 限时1分钟），点击「知道了，开始」
4. 左右滑动屏幕控制接物篮移动，点击左上角 ⏸ 可暂停

## 目录结构

```
minigame/
├── index.html      # 游戏主页面（唯一入口，CSS/JS 已内嵌）
├── images/         # 图片资源文件夹
│   ├── README.txt  # 图片说明
│   ├── basket.png  # 聚宝盆（可替换）
│   ├── hyr.png     # 普普（可替换）
│   ├── star_yes.png  # 西达肯定（可替换）
│   ├── gjh.png     # 小高（可替换）
│   ├── star_no.png # 西达否定（可替换）
│   └── background.png  # 背景图（可选，建议 9:16 比例如 450×800）
└── README.md       # 本说明文件
```

## 如何替换自定义图片

1. 将你的图片放入 `images` 文件夹
2. **保持文件名不变**（如 `basket.png`、`hyr.png`）
3. 需使用 **PNG** 格式（与代码中路径一致），建议 **1:1 比例**（正方形）
4. 若某张图片缺失，游戏会自动用彩色方块+文字占位，不影响运行

## 如何修改游戏参数

打开 `index.html`，在 `<script>` 里找到 `CONFIG` 对象，可修改：

| 参数 | 说明 | 默认值 |
|------|------|--------|
| `baseFallSpeed` | 基础掉落速度 | 2 |
| `speedIncreasePer100` | 每 100 分速度提升比例 | 0.1 |
| `maxSpeedMultiplier` | 最大速度倍数 | 2.5 |
| `basePenaltyChance` | 惩罚道具初始概率 | 0.1 |
| `maxPenaltyChance` | 惩罚道具最高概率 | 0.3 |
| `spawnInterval` | 物品生成间隔(ms) | 1200 |
| `minSpawnInterval` | 最小生成间隔(ms) | 400 |
| `initialLives` | 初始生命值 | 3 |
| `timedModeDuration` | 限时模式时长(秒) | 60 |
| `timedModeSpeedMultiplier` | 限时模式速度倍数 | 1.6 |
| `timedModeSpawnInterval` | 限时模式物品生成间隔(ms) | 800 |
| `pupuValue` | 普普单个计分 | 1 |
| `xidakendingValue` | 西达肯定单个计分 | 3 |
| `xiaogaoPenalty` | 小高扣分 | 10 |
| `scoreItemWeights.pupu` | 普普出现权重 | 0.75 |
| `scoreItemWeights.xidakending` | 西达肯定出现权重 | 0.25 |

修改后保存文件即可生效。

## 如何打包和分享给朋友

1. 将整个 `minigame` 文件夹打包为 ZIP
2. 发给朋友，朋友解压后用浏览器打开 `index.html` 即可
3. 无需联网、无需安装，支持手机浏览器直接运行

## 技术说明

- 纯 HTML5 + CSS + JavaScript，无任何框架和外部依赖
- 所有资源采用相对路径，便于打包分发
- 高分记录保存在浏览器 localStorage
- 支持触摸滑动和鼠标拖拽（电脑上也可玩）
