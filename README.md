

# 2026 Interactive New Year Greeting

这是一个基于 **Astro** 和 **HTML5 Canvas** 开发的 2026 新年互动祝福网页（事实上你可以随意修改为任何节日甚至是Ta的生日）。

项目采用纯静态前端技术栈，通过粒子系统实现了文字变换、3D 旋转圆环、物理引擎烟花以及隐藏彩蛋功能。旨在提供一个高性能、强交互的数字化贺卡体验。

> **预览链接**: [2026新年祝福](https://zh.maxtonniu.com/newyear/)

## 功能特性

* **高性能粒子动画**：基于 Canvas 2D 的粒子汇聚与散开效果，支持数千个粒子流畅运行。
* **3D 旋转圆环**：模拟 3D 透视的文字圆环，支持惯性拖拽交互（PC/移动端适配）。
* **物理模拟烟花**：包含重力、阻力、风力模拟的烟花系统，支持普通花火与“文字烟花”模式。
* **隐藏彩蛋机制**：通过快速旋转圆环触发隐藏的“极速模式”和解密信息。
* **URL 定制与分享**：利用 `lz-string` 压缩算法，支持通过 URL 参数生成包含自定义名字和隐藏祝福语的专属链接，无后端依赖。
* **音频系统**：集成背景音乐 (BGM) 和多层级烟花音效 (SFX)，支持 Web Audio API 交互解锁，完美支持苹果安卓电脑端浏览器要求。

## 关于 AI 辅助

本项目的部分核心逻辑与代码优化由 AI 辅助完成，如果你有严重的歧视和ai仇视就不用看了。

* 代码架构重构与 Astro 环境适配。
* 部分数学公式推导（3D 投影、粒子物理）。
* 性能优化建议（离屏渲染、渲染队列管理）。
* 部分词汇的润色及注释细节

## 项目结构与资源说明

本项目是一个标准的 Astro 项目，核心逻辑集中在单页中。

```text
/
├── public/
│   ├── audio/              # 音频资源文件夹
│   │   ├── bgm/            # 背景音乐 (随机播放)
│   │   ├── lift*.mp3       # 烟花升空音效
│   │   ├── burst*.mp3      # 烟花爆炸音效
│   │   └── ...
│   ├── fonts/              # 字体文件 (如 .otf/.ttf)
│   └── scripts/
│       └── lz-string.min.js # 用于URL参数压缩的工具库
├── src/
│   └── pages/
│       └── index.astro     # 核心代码文件 (HTML/CSS/JS 都在这里)
├── astro.config.mjs        # Astro 配置文件
└── package.json

```

## 如何使用

本项目基于 Astro 框架构建。

1. **克隆或下载本项目**

2. **安装依赖**
   
   ```bash
   npm install
   ```

    3.启动本地开发服务器

```bash
npm run dev
```

访问 `http://localhost:4321` 查看效果。
4. **构建生产版本**

```bash
npm run build
```

构建后的静态文件将位于 `dist/` 目录下。

## 配置与自定义

所有可调节参数均位于 `src/pages/index.astro` 脚本顶部的 `CONFIG` 对象中。你可以修改以下内容而无需改动核心逻辑：

* **urlConfig**: URL 参数的键名与错误提示。
* **textLogic**: 祝福语词库、随机抽取数量。
* **fontSizes**: 不同屏幕尺寸下的文字大小。
* **fireworks**: 烟花上升速度、爆炸范围、文字烟花出现的概率。
* **music/sound**: 音量初始值、资源路径。

## 移植指南

如果你想将此页面移植到其他非 Astro 的网站（如纯 HTML 环境或 Vue/React 项目）：

1. **资源迁移**：将 `public/` 目录下的 audio, fonts, scripts 文件夹复制到你目标项目的静态资源目录。
2. **代码剥离**：
* 打开 `src/pages/index.astro`。
* 复制 `<style>` 标签内的 CSS 到你的 CSS 文件中。
* 复制 `<body>` 标签内的 HTML 结构（`canvas` 和 UI 元素）。
* 复制 `<script>` 标签内的 JS 代码。**注意**：Astro 默认处理了顶层 await 和模块导入，移植到普通 HTML 时，请确保正确引入 `lz-string`，并将 JS 逻辑包裹在 `window.onload` 或 `DOMContentLoaded` 中。
  
  

## 参考与致谢

* **烟花物理引擎**：
  本项目的烟花粒子物理逻辑参考了开源项目 **Firework_Simulator**。
  原项目链接: [NianBroken/Firework_Simulator: 烟花模拟器，一个可以模拟各种烟花效果的网页|它可以展示各种绚丽多彩的烟花效果，并让人仿佛置身于真实烟花的绚丽世界之中。|模拟烟花|烟花网页|烟花绽放|烟花效果](https://github.com/NianBroken/Firework_Simulator)

## 许可证 (License)

本项目采用[Apache License, Version 2.0 | Apache Software Foundation](https://www.apache.org/licenses/LICENSE-2.0)许可证。

简而言之，你可以自由使用、修改和分享本项目的代码，但前提是：

1. 在其衍生作品中必须保留原始许可证和版权信息。
2. 必须以相同的许可证发布所有修改过的代码。

`Copyright © 2026 [Maxton/Maxthten]`








