# 风精灵 Codex 宠物

“风精灵”是一只可爱、懵懂、单纯的单翼风元素精灵。本仓库中的正式版本遵循以下固定设计：

- 所有动画帧只保留画面左侧的一组三片白色羽翼。
- 画面右侧没有翅膀、翼根或残翼。
- 风精灵没有手和手臂，不使用手部动作或手持道具。
- 打招呼动画仅通过画面左侧的单翼扇动表达。
- 头顶只保留指定一侧的双叶呆毛。

## 安装所需文件

安装时只需要仓库 `wind-spirit` 目录中的两个正式文件：

```text
wind-spirit/pet.json
wind-spirit/spritesheet.webp
```

其他文件的用途：

- `spritesheet.png`：便于查看或后续编辑的 PNG 图集，Codex 运行时不需要。
- `preview/`：静态预览、动画 GIF 和动作总览，Codex 运行时不需要。
- `qa/`：制作与质检记录，Codex 运行时不需要。

## 在另一台 Windows 电脑上安装

### 1. 下载宠物文件

可以使用以下任一方式获取本仓库：

- 在 GitHub 仓库页面选择 **Code → Download ZIP**，然后完整解压。
- 从 GitHub Releases 下载发布的 ZIP，并完整解压。
- 使用 Git 克隆仓库。

不要直接在压缩包预览窗口中复制文件，先将 ZIP 完整解压到普通文件夹。

### 2. 创建 Codex 宠物目录

在文件资源管理器地址栏输入：

```text
%USERPROFILE%\.codex\pets
```

在 `pets` 文件夹中创建名为 `wind-spirit` 的文件夹。最终路径应为：

```text
C:\Users\你的用户名\.codex\pets\wind-spirit\
```

如果 `.codex` 或 `pets` 文件夹尚不存在，可以手动逐级创建。

也可以在 PowerShell 中运行：

```powershell
$target = Join-Path $env:USERPROFILE '.codex\pets\wind-spirit'
New-Item -ItemType Directory -Force -Path $target
```

### 3. 复制正式文件

将仓库 `wind-spirit` 目录中的以下两个文件复制到 Codex 的 `wind-spirit` 宠物文件夹：

```text
wind-spirit/pet.json
wind-spirit/spritesheet.webp
```

正确的安装结构如下：

```text
C:\Users\你的用户名\.codex\pets\wind-spirit\
├─ pet.json
└─ spritesheet.webp
```

不要形成额外的嵌套目录，例如下面这种结构是错误的：

```text
C:\Users\你的用户名\.codex\pets\wind-spirit\wind-spirit-codex-pet\pet.json
```

如果 PowerShell 当前目录就是已解压的仓库根目录，也可以运行：

```powershell
$target = Join-Path $env:USERPROFILE '.codex\pets\wind-spirit'
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item -LiteralPath '.\wind-spirit\pet.json' -Destination $target -Force
Copy-Item -LiteralPath '.\wind-spirit\spritesheet.webp' -Destination $target -Force
```

### 4. 在 Codex 中启用

1. 打开 Codex 桌面应用。
2. 进入 **设置 → 宠物**。
3. 点击 **刷新**。
4. 在自定义宠物列表中找到 **风精灵**。
5. 选择 **风精灵**，确认它显示为 **已选**。
6. 点击 **唤醒宠物**。

如果安装时 Codex 已经打开，而刷新后仍未出现“风精灵”，请完全退出 Codex 后重新打开，再次进入宠物设置。

## 安装验证

`pet.json` 中应包含以下关键设置：

```json
{
  "id": "wind-spirit",
  "displayName": "风精灵",
  "spriteVersionNumber": 2,
  "spritesheetPath": "spritesheet.webp"
}
```

正式图集规格：

- 尺寸：`1536 × 2288`
- 排列：`8 × 11`
- 图集版本：Codex v2
- 背景：透明

可使用 PowerShell 校验正式文件：

```powershell
Get-FileHash -Algorithm SHA256 '.\wind-spirit\pet.json'
Get-FileHash -Algorithm SHA256 '.\wind-spirit\spritesheet.webp'
```

正确的 SHA-256：

```text
wind-spirit/pet.json
B9A53754C039CA2EA623CF4F8D683EA7DA94854C10BE9461047FAAA2998BD168

wind-spirit/spritesheet.webp
1A6B19EFA5F1399B7F31487AF308C0B983411CDE0F59E9781B2EE57D0B76C694
```

## 常见问题

### 宠物列表中没有“风精灵”

依次检查：

1. 文件夹名称是否为 `wind-spirit`。
2. `pet.json` 和 `spritesheet.webp` 是否直接位于该文件夹中。
3. 文件扩展名是否正确，没有变成 `pet.json.txt`。
4. ZIP 是否已经完整解压。
5. 是否点击了宠物设置中的 **刷新**。
6. 完全退出并重新打开 Codex。

### 能看到宠物名称，但无法显示动画

检查 `spritesheet.webp` 是否完整下载，并确认 `pet.json` 中的 `spritesheetPath` 仍为：

```json
"spritesheetPath": "spritesheet.webp"
```

可以使用上面的 SHA-256 校验值确认文件没有损坏。

### 显示的不是单翼无手版本

请确认安装的是本仓库的正式 `spritesheet.webp`，并删除或替换同一安装目录中的旧图集。替换后点击 **刷新**，必要时重启 Codex。

## 更新宠物

更新到新版本时：

1. 先在 Codex 中收起宠物。
2. 使用新版 `pet.json` 和 `spritesheet.webp` 覆盖安装目录中的旧文件。
3. 返回 **设置 → 宠物** 并点击 **刷新**。
4. 重新选择并唤醒“风精灵”。

## 授权许可

本项目采用《风精灵个人使用许可证 1.0》。允许个人用户下载并安装到本人拥有或
控制的个人电脑，仅限私人、非商业用途；禁止商用、转载、再分发和二次发布。

完整条款请参阅 [`LICENSE`](./LICENSE)。本许可证不是开源软件许可证。

## 质检状态

- 标准动画逐帧结构检查：通过。
- Codex v2 图集校验：通过，无错误或警告。
- 三人隔离方向盲测：硬性基准方向全部通过。
- 最终独立视觉 QA：通过，所有动画均符合单翼、无手规则。
