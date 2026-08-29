# Unity 项目配置指南

## 项目信息
- **项目名称**: Island Survival
- **Unity 版本**: 2022.3 LTS
- **目标平台**: 微信小游戏 / WebGL
- **渲染管线**: Built-in Render Pipeline

## 快速开始

### 1. 创建 Unity 项目
```bash
# 使用 Unity Hub 创建新项目
# 项目路径: F:/FGame/源码/Unity
# 模板: 3D (URP 或 Built-in)
```

### 2. 导入脚本
将所有 `.cs` 文件复制到:
```
Assets/Scripts/
├── Core/
├── Resource/
├── Building/
├── Water/
├── Enemy/
├── Combat/
├── Scenes/
├── UI/
├── Input/
└── Editor/
```

### 3. 创建场景
在 Unity Editor 中:
1. File → New Scene
2. 保存为 `Assets/Scenes/Chapter1.unity`
3. 添加以下空物体作为根节点:
   - GameManager
   - ResourceManager
   - CombatController
   - BuildingGrid
   - WallManager
   - EnemySpawner
   - WaterSystem
   - SceneLoader
   - InputManager
   - Chapter1Builder

### 4. 添加脚本组件
为每个空物体添加对应的脚本组件。

### 5. 运行测试
点击 Play 按钮测试第1章流程。

## 场景结构

```
Chapter1
├── GameManager (GameManager + GameBootstrapper)
├── ResourceManager (ResourceManager)
├── CombatController (CombatController)
├── BuildingGrid (BuildingGrid)
├── WallManager (WallManager)
├── EnemySpawner (EnemySpawner)
├── WaterSystem (WaterSystem)
├── SceneLoader (SceneLoader)
├── InputManager (InputManager)
├── Chapter1Builder (Chapter1Builder)
├── Player (PlayerController)
├── UI Canvas
│   ├── ResourceUI
│   └── SubtitleManager
└── 场景对象
    ├── Water (平面)
    ├── Island (立方体)
    └── WheatField (触发器)
```

## 测试控制

| 按键 | 功能 |
|------|------|
| WASD / 方向键 | 移动 |
| 鼠标左键 | 攻击 |
| B | 建造围墙 |
| U | 升级 |
| 空格 | 下一章节 |

## 性能优化建议

1. **对象池**: 为敌人和子弹实现对象池
2. **LOD**: 远距离使用低多边形模型
3. **图集**: 合并 UI 纹理到图集
4. **异步加载**: 大场景使用异步加载

## 发布设置

### 微信小游戏
1. File → Build Settings
2. 选择 WebGL 平台
3. 点击 Switch Platform
4. 使用微信开发者工具导入

### 独立版本
1. File → Build Settings
2. 选择 PC, Mac & Linux Standalone
3. 点击 Build
4. 测试并发布
