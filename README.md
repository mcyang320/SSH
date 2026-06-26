# SSH Pet

**中文** | [English](#english)

A cute little girl inspired by YMC's girlfriend.

![SSH Pet demo](assets/gifs/ssh-pet-demo.gif)

## 中文

SSH Pet 是一个按 Codex 宠物标准制作的像素风小女孩宠物包。角色是长卷发、灰色针织背心、白衬衫、黑色百褶短裙、黑色过膝袜和白色运动鞋的可爱小女孩，灵感来源于 YMC's girlfriend。

## 安装

把这个目录放到 Codex 的 pets 目录：

```bash
cp -R ssh-pet ~/.codex/pets/ssh-pet
```

核心文件只有两个：

- `pet.json`
- `spritesheet.webp`

其他 `assets/` 文件是预览、README 展示、GIF 和 Live Photo/视频导出素材。

## 标准状态

| 状态 | 说明 | 预览 |
|---|---|---|
| `idle` | 待机、眨眼、微笑 | ![idle](assets/gifs/states/idle.gif) |
| `running-right` | 向右拖拽，惊慌失措 | ![running-right](assets/gifs/states/running-right.gif) |
| `running-left` | 向左拖拽，惊慌失措 | ![running-left](assets/gifs/states/running-left.gif) |
| `waving` | 挥手 | ![waving](assets/gifs/states/waving.gif) |
| `jumping` | 蹦蹦跳跳 | ![jumping](assets/gifs/states/jumping.gif) |
| `failed` | 委屈哭泣，保持站立微曲膝 | ![failed](assets/gifs/states/failed.gif) |
| `waiting` | 等待输入或确认 | ![waiting](assets/gifs/states/waiting.gif) |
| `running` | 工作中/处理中 | ![running](assets/gifs/states/running.gif) |
| `review` | 自然掏手机、刷手机、放回 | ![review](assets/gifs/states/review.gif) |

## 额外动作

这些 GIF 不属于 Codex 固定 9 行 atlas，但已经放在包里用于展示和分享。

| 动作 | 说明 | 预览 |
|---|---|---|
| `blink` | 眨眼 | ![blink](assets/gifs/extras/blink.gif) |
| `smile` | 微笑 | ![smile](assets/gifs/extras/smile.gif) |
| `bouncy` | 蹦跳 | ![bouncy](assets/gifs/extras/bouncy.gif) |
| `sleepy` | 打瞌睡 | ![sleepy](assets/gifs/extras/sleepy.gif) |
| `humming` | 闭眼、双手放胸前、头部摇晃、彩色音符 | ![humming](assets/gifs/extras/humming.gif) |
| `dragging-panicked` | 拖拽时惊慌失措 | ![dragging-panicked](assets/gifs/extras/dragging-panicked.gif) |

## 文件结构

```text
ssh-pet/
  pet.json
  spritesheet.webp
  assets/
    gifs/
      ssh-pet-demo.gif
      states/*.gif
      extras/*.gif
    live-photo/
      ssh-pet-live.jpg
      ssh-pet-live.mov
      ssh-pet-social.mp4
    qa/
      contact-sheet.png
      validation.json
```

## QA

- `spritesheet.webp` 尺寸：`1536x1872`
- 单帧尺寸：`192x208`
- 布局：8 列 x 9 行
- 背景：透明
- 校验：`assets/qa/validation.json`
- 边缘检查：`assets/qa/edge-diagnostics.json`

## English

SSH Pet is a Codex pet package featuring a cute little pixel-art girl inspired by YMC's girlfriend. She has long wavy dark-brown hair, a gray knit vest over a white shirt, a black pleated skirt, black over-knee socks, and white sneakers.

## Installation

Copy this folder into your Codex pets directory:

```bash
cp -R ssh-pet ~/.codex/pets/ssh-pet
```

Codex only needs:

- `pet.json`
- `spritesheet.webp`

The `assets/` folder contains previews, per-state GIFs, extra idle actions, QA images, and social/live-photo exports.

## Standard States

The standard atlas includes `idle`, `running-right`, `running-left`, `waving`, `jumping`, `failed`, `waiting`, `running`, and `review`. The `review` state naturally takes out a phone, scrolls, then puts it away. The drag states use a panicked expression with limb motion instead of simple whole-body shaking.

## Extra Actions

Extra GIFs include blink, smile, bouncy, sleepy, humming, and dragging-panicked. The humming action has closed eyes, both hands on the chest, a swaying head, and colorful music notes.
