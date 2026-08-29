# Unity Editor 使用指南

## 当前状态
- ✅ Unity Hub 已启动
- ⏳ 需要导入 Unity 项目
- ⏳ 需要安装 Unity 2022.3 LTS

---

## 快速开始

### 步骤1: 在 Unity Hub 中打开项目
```
Unity Hub → Projects → Open
选择路径: F:/FGame/源码/Unity
```

### 步骤2: 等待项目加载
- 首次加载需要编译脚本（约1-2分钟）
- 查看 Console 窗口确认无错误

### 步骤3: 自动搭建场景
```
菜单栏 → IslandSurvival → 自动搭建第1章场景
```

### 步骤4: 运行游戏
```
点击 Play 按钮 (顶部中间)
```

### 步骤5: 测试控制
| 按键 | 功能 |
|------|------|
| W/A/S/D | 移动玩家 |
| 鼠标左键 | 攻击敌人 |
| B | 建造围墙 |
| U | 升级建筑 |
| 空格 | 下一章 |

---

## 常见问题

### Q: Unity 提示缺少模块
**A**: 在 Unity Hub 中安装 Unity 2022.3 LTS
- Windows Build Support (IL2CPP)
- WebGL Support

### Q: 编译错误
**A**: 检查脚本路径，确保所有文件在正确位置

### Q: 场景为空
**A**: 运行 `IslandSurvival → 自动搭建第1章场景`

---

## 菜单命令

```
IslandSurvival
├── 自动搭建第1章场景    # 创建测试场景
├── 创建预制体模板       # 生成基础Prefab
├── 配置微信小游戏参数   # 设置发布参数
├── 完整构建流程         # 打包所有平台
├── 运行单元测试         # 执行测试
└── 性能基准测试         # 性能分析
```

---

## 项目结构

```
F:/FGame/源码/Unity/Assets/
├── Scripts/
│   ├── Core/          # 游戏核心
│   ├── Resource/      # 资源管理
│   ├── Building/      # 建筑系统
│   ├── Water/         # 水管系统
│   ├── Enemy/         # 敌人系统
│   ├── Combat/        # 战斗系统
│   ├── Scenes/        # 场景管理
│   ├── UI/            # 界面
│   ├── Input/         # 输入
│   ├── Economy/       # 经济
│   ├── SaveSystem/    # 存档
│   ├── Config/        # 配置
│   └── Editor/        # 编辑器工具
├── Tests/             # 测试套件
└── Scenes/            # Unity场景
```

---

## 下一步

1. **等待 Unity Hub 加载完成**
2. **点击 Open Project**
3. **等待脚本编译**
4. **运行测试场景**
5. **报告测试结果**
