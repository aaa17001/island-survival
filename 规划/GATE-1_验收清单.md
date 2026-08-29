# GATE-1 验收清单

## 核心玩法验证

### 移动系统 ✅
- [x] 玩家角色存在
- [x] 移动脚本已实现
- [ ] **待验证**: Unity Play Mode 中实际移动测试

### 战斗系统 ✅
- [x] CombatController 已实现
- [x] Enemy 基类已实现
- [x] EnemySpawner 已实现
- [ ] **待验证**: 实际战斗测试

### 建筑系统 ✅
- [x] BuildingGrid 网格系统
- [x] WallManager 围墙管理
- [x] 资源消耗逻辑
- [ ] **待验证**: 实际建造测试

### 剧情系统 ✅
- [x] Chapter1Manager 章节管理
- [x] SubtitleManager 字幕系统
- [x] 6步剧情流程
- [ ] **待验证**: 完整剧情播放

## 测试环境准备

### Unity Editor 设置
```
项目路径: F:/FGame/源码/Unity
Unity版本: 2022.3 LTS
渲染管线: Built-in
```

### 场景对象清单
```
空物体:
├── GameManager
├── ResourceManager
├── CombatController
├── BuildingGrid
├── WallManager
├── EnemySpawner
├── WaterSystem
├── SceneLoader
├── InputManager
├── Chapter1Complete
└── Chapter1Builder

预制体（待创建）:
├── Player.prefab
├── Enemy_Savage.prefab
├── Enemy_CowThief.prefab
├── Wall.prefab
├── FishFarm.prefab
├── Pasture.prefab
└── WheatField.prefab
```

### 测试步骤
1. **启动 Unity Editor**
   - 打开 `F:/FGame/源码/Unity`
   - 等待项目导入完成

2. **创建场景**
   - File → New Scene
   - 保存为 `Assets/Scenes/Chapter1.unity`

3. **添加对象**
   - 按照场景对象清单添加空物体
   - 挂载对应脚本组件

4. **运行测试**
   - 点击 Play 按钮
   - 按 WASD 移动
   - 按 B 建造围墙
   - 按 鼠标左键 攻击
   - 按 空格 下一章

## 验收标准

### 必须通过
- [ ] 玩家可移动（WASD）
- [ ] 可建造围墙（B键）
- [ ] 可攻击敌人（鼠标左键）
- [ ] 资源正确消耗
- [ ] 字幕正确显示
- [ ] 章节可推进

### 建议通过
- [ ] 帧率稳定 60fps
- [ ] 无崩溃或卡死
- [ ] 无严重 Bug

## 已知问题

| 问题 | 状态 | 解决方案 |
|------|------|----------|
| 缺少预制体 | 待处理 | 在 Unity 中手动创建 |
| 水面材质 | 待处理 | 使用默认材质替代 |
| 敌人AI | 待实现 | 简化为直线移动 |

## 下一步行动

1. 打开 Unity Editor
2. 按照场景对象清单搭建
3. 运行 Play Mode 测试
4. 记录测试结果
5. 修复发现的问题
