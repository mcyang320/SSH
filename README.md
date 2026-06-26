# SSH

**中文** | [English](#english)

A cute little girl inspired by YMC's girlfriend.

![SSH demo](assets/gifs/SSH-demo.gif)

## 中文

SSH 是一个按 Codex 宠物标准制作的像素风小女孩宠物包。角色是长卷发、灰色针织背心、白衬衫、黑色百褶短裙、黑色过膝袜和白色运动鞋的可爱小女孩，灵感来源于 YMC's girlfriend。

## 安装

把这个目录放到 Codex 的 pets 目录：

```bash
cp -R SSH ~/.codex/pets/SSH
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
| `running-left` | 向左拖拽，单独绘制避免镜像穿模 | ![running-left](assets/gifs/states/running-left.gif) |
| `waving` | 挥手 | ![waving](assets/gifs/states/waving.gif) |
| `jumping` | 鼠标选中反馈：闭眼哼歌 | ![jumping](assets/gifs/states/jumping.gif) |
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
| `hair-fix-selected` | 选中时整理发型 | ![hair-fix-selected](assets/gifs/extras/hair-fix-selected.gif) |
| `sleepy` | 打瞌睡 | ![sleepy](assets/gifs/extras/sleepy.gif) |
| `humming` | 闭眼、双手放胸前、头部摇晃、彩色音符 | ![humming](assets/gifs/extras/humming.gif) |
| `dragging-panicked` | 向右拖拽时惊慌失措 | ![dragging-panicked](assets/gifs/extras/dragging-panicked.gif) |
| `dragging-panicked-left` | 向左拖拽时惊慌失措，单独绘制 | ![dragging-panicked-left](assets/gifs/extras/dragging-panicked-left.gif) |


## 触发逻辑

Codex pet 的 atlas 行是固定协议，视觉动作需要放在对应行里：

| 行 | 状态 | 通常触发 | 本包动作 |
|---|---|---|---|
| 0 | `idle` | 无任务时待机 | 呼吸、眨眼、微笑 |
| 1 | `running-right` | 向右拖拽宠物 | 惊慌失措地被拖向右边 |
| 2 | `running-left` | 向左拖拽宠物 | 惊慌失措地被拖向左边 |
| 3 | `waving` | 打招呼/唤起注意 | 挥手 |
| 4 | `jumping` | 鼠标 hover/点击/选中反馈，协议名仍叫 jumping | 闭眼哼歌，双手放胸前，头部摇晃，带彩色音符 |
| 5 | `failed` | 失败、取消、卡住 | 站着委屈哭泣，只微曲膝 |
| 6 | `waiting` | 等待用户确认或输入 | 双手放前、耐心等待 |
| 7 | `running` | 任务运行中 | 思考/忙碌处理的小动作 |
| 8 | `review` | 结果完成，等待查看 | 自然掏手机、刷手机、放回 |

`jumping` 行现在使用现成的哼歌动作作为选中反馈。`sleepy`、`blink`、`hair-fix-selected` 等额外 GIF 放在 `assets/gifs/extras/`，它们是分享/展示素材，不会被 Codex 的固定 atlas 自动触发。

## 文件结构

```text
SSH/
  pet.json
  spritesheet.webp
  assets/
    gifs/
      SSH-demo.gif
      states/*.gif
      extras/*.gif
    live-photo/
      SSH-live.jpg
      SSH-live.mov
      SSH-social.mp4
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

SSH is a Codex pet package featuring a cute little pixel-art girl inspired by YMC's girlfriend. She has long wavy dark-brown hair, a gray knit vest over a white shirt, a black pleated skirt, black over-knee socks, and white sneakers.

## Installation

Copy this folder into your Codex pets directory:

```bash
cp -R SSH ~/.codex/pets/SSH
```

Codex only needs:

- `pet.json`
- `spritesheet.webp`

The `assets/` folder contains previews, per-state GIFs, extra idle actions, QA images, and social/live-photo exports.

## Standard States

The standard atlas includes `idle`, `running-right`, `running-left`, `waving`, `jumping`, `failed`, `waiting`, `running`, and `review`. The `review` state naturally takes out a phone, scrolls, then puts it away. The drag states use a panicked expression with limb motion instead of simple whole-body shaking.


## Trigger Mapping

Codex uses a fixed 9-row atlas. This package maps the rows as follows: `idle` for resting, `running-right` and `running-left` for drag direction, `waving` for greeting/attention, `jumping` for mouse hover/click/selection feedback, `failed` for failed or cancelled work, `waiting` for user confirmation, `running` for active task processing, and `review` for completed output review.

The protocol row is still named `jumping`, but the visual action is the existing humming animation: closed eyes, both hands on the chest, a swaying head, and colorful music notes. Extra GIFs such as `sleepy`, `blink`, and `hair-fix-selected` are included for sharing and README previews; they are not auto-triggered by the fixed Codex atlas.

## Extra Actions

Extra GIFs include blink, smile, hair-fix-selected, sleepy, humming, and dragging-panicked. The humming action has closed eyes, both hands on the chest, a swaying head, and colorful music notes.
