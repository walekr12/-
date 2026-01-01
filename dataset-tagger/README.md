# AI 数据集打标器 (Dataset Tagger)

一个现代化的 AI 训练数据集标签管理工具，基于 Wails + Vue3 + Tailwind CSS 构建。

![界面预览](docs/preview.png)

## ✨ 特性

- 🖼️ **智能文件配对** - 自动匹配图片/视频文件与对应的 txt 标签文件
- 🏷️ **标签词频分析** - 自动统计所有标签的出现频率并排名显示
- 🎯 **标签筛选** - 点击标签即可筛选包含该标签的所有项目
- 📦 **批量操作** - 支持批量添加、删除、替换标签，支持正则表达式
- 🎬 **视频支持** - 自动提取视频中间帧作为缩略图预览
- 💾 **一键保存** - 统一保存所有修改，避免遗漏
- 🎨 **科技感UI** - 霓虹风格的现代界面设计
- 📄 **分页浏览** - 支持大量数据的分页显示

## 🚀 快速开始

### 下载预编译版本

从 [Releases](../../releases) 页面下载对应平台的预编译版本：
- Windows: `dataset-tagger-windows.exe`
- macOS: `dataset-tagger-macos.app`
- Linux: `dataset-tagger-linux`

### 从源码构建

#### 前置要求
- Go 1.21+
- Node.js 18+
- [Wails CLI](https://wails.io/docs/gettingstarted/installation)
- FFmpeg (用于视频缩略图生成)

#### 构建步骤

```bash
# 克隆仓库
git clone https://github.com/walekr12/-

# 进入项目目录
cd dataset-tagger

# 安装前端依赖
cd frontend && npm install && cd ..

# 开发模式运行
wails dev

# 构建发行版
wails build
```

## 📖 使用说明

### 1. 导入数据集

点击「导入文件夹」按钮，选择包含图片/视频和对应 txt 文件的文件夹。

文件命名规则：
```
image001.jpg  ←→  image001.txt
video002.mp4  ←→  video002.txt
```

### 2. 浏览和筛选

- 左侧面板显示所有标签的词频统计
- 点击标签可筛选包含该标签的项目
- 使用搜索框快速查找标签

### 3. 编辑标签

- 点击任意卡片进入编辑模式
- 修改标签内容（逗号分隔）
- 点击保存或按 Ctrl+S

### 4. 批量操作

1. 点击「批量操作」按钮展开面板
2. 勾选要操作的项目（或使用全选）
3. 选择操作类型：
   - **添加标签**: 在开头或末尾添加新标签
   - **删除标签**: 删除匹配的标签
   - **替换标签**: 将旧标签替换为新标签
4. 支持正则表达式匹配

### 5. 保存修改

- 修改后的项目会显示黄色标记
- 点击「保存全部」一次性保存所有修改

## 🛠️ 技术栈

| 组件 | 技术 |
|------|------|
| 桌面框架 | [Wails v2](https://wails.io/) |
| 后端语言 | Go 1.21 |
| 前端框架 | Vue 3 |
| 样式 | Tailwind CSS |
| 构建工具 | Vite |
| 视频处理 | FFmpeg |

## 📁 项目结构

```
dataset-tagger/
├── main.go              # Wails 入口
├── app.go               # Go 后端核心逻辑
├── wails.json           # Wails 配置
├── frontend/
│   ├── src/
│   │   ├── App.vue      # 主组件
│   │   ├── main.js      # 入口
│   │   └── styles/      # 样式文件
│   ├── package.json
│   └── vite.config.js
└── .github/workflows/   # CI/CD 配置
```

## 🔧 配置

### FFmpeg 安装

视频缩略图生成需要 FFmpeg：

**Windows:**
```powershell
# 使用 Chocolatey
choco install ffmpeg

# 或下载二进制文件
# https://ffmpeg.org/download.html
```

**macOS:**
```bash
brew install ffmpeg
```

**Linux:**
```bash
sudo apt install ffmpeg
```

## 📝 License

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！
