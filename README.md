# 大透视产品海报 · perspective-product-poster

用产品图制作具有极近距离超广角、显著近大远小和动态人物互动的产品海报。适用于运动、数码、饮品、食品、美妆等需要潮流感、冲击力与视觉张力的创意视觉。

默认生成 **1张2:3竖版海报**，使用 **Codex内置生图**，先展示完整中文提示词，再自动生成。**不新增标题、广告文案、背景品牌大字或装饰文字**；保留产品本身已有的标识、标签与文字。

## 准备材料

| 材料 | 是否必需 | 用途 |
| --- | --- | --- |
| 产品图 | 必需 | 确定外形、结构、固有色、材质与可辨识的标识 |
| 风格参考图 | 选填 | 提炼色彩、影调、光线、材质、画面质感与情绪 |
| 模特参考图 | 选填 | 确定人物外貌、发型、肤色和体态 |
| 透视或动作参考图 | 选填 | 仅参考机位、姿态与空间层次；不自动继承人物外貌 |

请说明每张参考图的用途。只提供产品图也可以完成；没有产品图时，需要先补充产品图。

## 使用方法

安装后上传产品图，在Codex中输入：

```text
用 $perspective-product-poster，根据我上传的产品图制作一张大透视产品海报。
```

正常流程：

1. 查看产品图，记录需要保持的外观与识别特征。
2. 有风格图时，梳理其视觉特征并等待确认；没有风格图时，推荐3个有实质区别的潮流方向供选择。
3. 风格确定后，自动补齐成年人物、穿搭、表情、动作，以及极近前景到远端身体的空间关系。
4. 输出可复制的完整中文提示词，自动调用生图，不再增加提示词审批环节。
5. 查看实际成图、核对宽高与视觉表现，交付图片及同名提示词文件。

用户明确说「风格由你定」「按参考直接生成」时，会说明采用的方向后继续执行，不重复等待风格确认。只要分析或提示词时，停在指定阶段。

## 常用调用示例

### 风格由AI决定，直接生成

上传产品图后输入：

```text
用 $perspective-product-poster，风格由你定，直接制作一张2:3竖版大透视海报。要有明显的近大远小、动态姿态和潮流感，不新增文案。
```

### 带风格参考

上传产品图和风格图，说明编号：

```text
用 $perspective-product-poster。图1是产品图，图2是风格参考。先提炼图2的色彩、影调、光线和质感，整理后让我确认；产品外观以图1为准。
```

### 只使用产品原图

```text
用 $perspective-product-poster，只使用我上传的产品原图作为图像参考。人物、场景和动作由你设计，人物自然开心，产品靠近镜头形成强透视。风格由你定，直接生成一张。
```

### 只参考姿势与构图

```text
用 $perspective-product-poster。图1是产品图；图2只参考人物姿势、机位和构图，不参考图2人物的外貌。重新设计一位成年人物，表情开心。按这个方向直接生成。
```

### 只输出提示词

```text
用 $perspective-product-poster，风格由你定，只输出完整中文提示词，先不要生图。
```

### 修改当前结果

```text
保持产品外观、已确定的色彩和场景，进一步拉近产品与镜头的距离，让连接产品的手臂明显缩短、脸部后退；把人物表情改为自信的浅笑，不新增文字。
```

## 视觉规则

- 强调极近距离超广角与连续纵深，允许适度鱼眼和倾斜机位；透视来自主体距离与空间层次。
- 产品是视觉主角，结构、材质和主要标识须可辨，握持或穿戴关系须可信。
- 风格保持潮流、力量感和视觉张力，不推荐小清新、柔美或轻柔治愈方案。
- 人物神态根据产品和当前要求设计，可开心、自信、俏皮或专注，无固定性别或穿搭。
- 不新增广告文案，不专门预留文案区，不扩写未经提供的功效、参数、价格或促销信息。

## 安装说明

### 方式一：让Codex或支持Skills的Agent安装

复制下面这段给Agent：

```text
请安装 https://github.com/youngerweb2026/perspective-product-poster 中的 skills/perspective-product-poster 目录，完整保留 SKILL.md 和 agents/openai.yaml。优先使用原生Skill安装器。已有同名版本时先比较并备份后更新。只安装，不启动生图，完成后告诉我调用方法。
```

更完整的跨环境安装指令见 [安装指令.txt](安装指令.txt)。其他Agent能否执行完整生成流程，取决于它实际提供的工具。

### 方式二：终端安装到Codex

需要安装Node.js，并可使用`npx`：

```bash
npx --yes skills add youngerweb2026/perspective-product-poster --skill perspective-product-poster --agent codex --global --yes
```

这条命令使用`skills`社区CLI。已有同名版本时，建议先用方式一核对和备份。安装完成后，在下一轮对话调用`$perspective-product-poster`；如果列表尚未刷新，可新开聊天或重新加载Codex。

### 方式三：使用Codex自带的Skill Installer

在带有系统Skill Installer的macOS/Linux Codex环境中执行：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo youngerweb2026/perspective-product-poster --path skills/perspective-product-poster
```

安装器默认安装到当前Codex的用户级Skills目录；如果目标已经存在会停止，避免直接覆盖。

也可下载仓库ZIP，将完整的`skills/perspective-product-poster`目录放到当前Agent实际使用的Skills目录中。

## 运行环境

本仓库提供Skill指令与界面配置，不自带图片模型或第三方平台账号。Codex中默认调用环境已有的`imagegen` Skill和内置生图工具。其他环境需要具备相应的参考图输入与图片生成能力；工具不可用时应如实说明，并保留完整提示词。

图片的实际尺寸、商品细字、人体接触和透视表现需要查看成图后核对。生成结果用于创意视觉，不作为产品实测或人物真实代言的证明。

## 文件结构

```text
skills/
└── perspective-product-poster/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
README.md
安装指令.txt
```

完整执行规则见 [SKILL.md](skills/perspective-product-poster/SKILL.md)。
