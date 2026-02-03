# 🥷🏽 NinjaSketch - 手绘风格白板应用

一款基于 React 和 TypeScript 开发的在线白板绘图应用，灵感来源于 Excalidraw。使用 Rough.js 实现了独特的手绘素描风格效果。

## ✨ 项目简介

NinjaSketch 是一个功能完善的白板绘图工具，支持多种绘图工具、元素操作和画布导航功能。项目采用现代前端技术栈，代码结构清晰，具有良好的可维护性和扩展性。

## 📦 技术栈

| 类别 | 技术 |
|------|------|
| 构建工具 | Vite |
| 前端框架 | React 18 |
| 开发语言 | TypeScript |
| 绘图引擎 | Rough.js |
| 手绘笔触 | Perfect Freehand |
| UI 组件 | Material UI |
| 样式方案 | CSS + CSS Variables |
| 单元测试 | Vitest |
| E2E 测试 | Cypress + Testing Library |

## 🦄 功能特性

### 🎨 绘图工具

- **铅笔工具** - 自由手绘，支持平滑笔触效果
- **直线工具** - 绘制手绘风格的直线
- **矩形工具** - 绘制手绘风格的矩形
- **文本工具** - 在画布上添加文字标注

### 🖱️ 元素操作

- **选择移动** - 选中元素后可自由拖拽移动
- **调整大小** - 拖拽矩形和直线的控制点进行缩放
- **撤销重做** - 完整的历史记录管理，支持多步撤销/重做

### 🔍 画布导航

- **平移画布** - 按住空格键拖拽或使用鼠标中键
- **缩放视图** - Ctrl + 滚轮或使用界面按钮进行缩放
- **缩放比例** - 支持 10% - 2000% 的缩放范围

### ⌨️ 快捷键

| 功能 | 快捷键 |
|------|--------|
| 平移画布 | `空格键` + 拖拽 / 鼠标中键 |
| 撤销 | `Ctrl/Cmd + Z` |
| 重做 | `Ctrl/Cmd + Y` 或 `Ctrl/Cmd + Shift + Z` |
| 放大 | `Ctrl/Cmd + 滚轮向上` |
| 缩小 | `Ctrl/Cmd + 滚轮向下` |

## 🏗️ 项目结构

```
src/
├── App.tsx                 # 主应用组件，包含核心绘图逻辑
├── types.ts                # TypeScript 类型定义
├── main.tsx                # 应用入口
├── index.css               # 全局样式
├── components/             # UI 组件
│   ├── action-bar/         # 工具栏组件
│   ├── control-panel/      # 控制面板（缩放、撤销重做）
│   └── info/               # 帮助信息弹窗
├── hooks/                  # 自定义 Hooks
│   ├── useHistory.ts       # 历史记录管理 Hook
│   └── usePressedKeys.ts   # 键盘按键状态 Hook
└── utilities/              # 工具函数
    ├── create-element.ts           # 创建绘图元素
    ├── draw-element.ts             # 渲染绘图元素
    ├── get-element-at-position.ts  # 元素位置检测
    ├── adjust-element-coordinates.ts # 坐标调整
    ├── cursor-for-position.ts      # 光标样式
    ├── near-point/                 # 点位判断工具
    └── resized-coordinates/        # 缩放坐标计算
```

## 🚀 快速开始

### 安装依赖

```bash
npm install
```

### 启动开发服务器

```bash
npm run dev
```

### 构建生产版本

```bash
npm run build
```

### 运行测试

```bash
# 单元测试
npm run test

# E2E 测试
npm run cy:open
```

## 🧠 核心实现

### useHistory Hook

自定义 Hook 实现了完整的历史状态管理：
- 维护历史记录数组和当前索引
- 支持状态覆写（用于连续操作如拖拽）
- 提供 `undo` 和 `redo` 方法

### 元素位置检测

- **直线** - 基于点到线段的距离计算
- **矩形** - 边界检测和四角控制点检测
- **铅笔** - 遍历所有点进行线段距离判断
- **文本** - 基于文本边界框的包含检测

### 坐标系统

- 支持画布平移（Pan Offset）
- 支持画布缩放（Scale）
- 正确处理鼠标坐标到画布坐标的转换

## 💡 技术亮点

1. **手绘风格渲染** - 使用 Rough.js 生成自然的手绘效果
2. **平滑笔触** - 集成 Perfect Freehand 实现专业级手写效果
3. **响应式交互** - 完善的鼠标事件处理和光标反馈
4. **类型安全** - 完整的 TypeScript 类型定义
5. **测试覆盖** - 包含单元测试和 E2E 测试

## 🔮 未来规划

- [ ] 添加更多绘图工具（圆形、箭头、橡皮擦）
- [ ] 支持颜色选择器
- [ ] 添加深色主题
- [ ] 支持文本样式（字体、大小、颜色）
- [ ] 导出为图片功能
- [ ] 添加更多快捷键
- [ ] 响应式适配
- [ ] 添加更多语言支持
