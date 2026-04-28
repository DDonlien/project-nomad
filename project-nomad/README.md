# Project Nomad（Demo）

类宝可梦、俯视角/轴侧表现、**同步回合制（30 Tick）**的写实奇幻游戏 Demo。  
核心目标：用 Godot 4.x + C# 验证 **“灵魂投射战斗”** 与 **“参数化 Hex-Block 格点逻辑”** 的可落地性。

## 核心支柱（不可偏离）
1. **写实奇幻**：自然/灵魂能量存在，但传统“魔法师”极度罕见；生物遵循生老病死。
2. **游牧部族**：玩家隶属部族，部族在大地图上动态移动（补给/存储中心）。
3. **灵魂共鸣（收服）**：不是捕捉，而是调频共鸣；玩家属性特质决定可共鸣范围。
4. **灵魂投射战斗**：战斗时意识投射进入宝可梦体内进行 1v1；遵循“非暴力原则”设定。
5. **参数化格点结算**：所有占用/技能/移动/遮挡都必须可由 **Hex + Block** 参数化描述，并严格对齐 Tick。

## 技术栈
- 引擎：Godot 4.x（建议 4.2+）
- 语言：C#（.NET）
- 视角：2.5D / Isometric（2D 模拟 3D）
- 深度/遮挡：Y-Sort + 参数化格子规则

## 目录结构
```
project-nomad/
  .agent
  .editorconfig
  .gitignore
  LICENSE
  README.md
  docs/
    GDD.md
```

## 快速开始（建议流程）
1. 安装 Godot 4.x（.NET 版本）。
2. 用 Godot 创建/导入项目到本仓库目录（后续会生成 `project.godot` 等文件）。
3. 按 `docs/GDD.md` 的 Roadmap，从 C# 逻辑底座开始实现：
   - Hex-Block 坐标系（Cube Coordinates → Godot 世界坐标）
   - Tick 调度器（`BattleClock` 0-29）
   - 体积占用与静态阻挡

## 约定
- **逻辑优先于动画**：动画可连续，但判定必须对齐 Tick。
- **禁止发散机制**：任何新机制必须与 `docs/GDD.md` 一致，且先写成文档再实现。

## 文档
- 设计核心规范（GDD）：见 `docs/GDD.md`

## 版权与许可
本仓库为商业作品的私有代码库，默认 **All Rights Reserved**。详见 `LICENSE`。
