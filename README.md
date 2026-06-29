# Smart Agrobot Lab 🤖🌾

<div align="center">

[![Website](https://img.shields.io/badge/Website-smart--ag.github.io-blue?style=flat-square)](https://smart-ag.github.io/)
[![GitHub](https://img.shields.io/badge/GitHub-Smart--Ag-green?style=flat-square&logo=github)](https://github.com/Smart-Ag)
[![University](https://img.shields.io/badge/University-NWAFU-success?style=flat-square)](https://www.nwafu.edu.cn/)

**智能农业机器人实验室官方网站**

*Agriculture Robotics | Computer Vision | Intelligent Control*

---

</div>

## 📖 关于实验室

智能农业机器人实验室（Smart Agrobot Lab）致力于开发和研究用于现代农业的机器人和自动化系统。我们的研究涵盖农业机器人的设计、计算机视觉、智能控制、精准农业等多个领域。

**实验室主任**: 傅隆生 (Fu Longsheng)  
**机构**: [西北农林科技大学](https://www.nwafu.edu.cn/) (Northwest A&F University)  
**地点**: 陕西省咸阳市

### 主要研究方向

- 🤖 **农业机器人** - 设计与制造、动力学与控制
- 👁️ **机器视觉** - 图像处理、目标检测、3D重建
- 🎯 **智能控制** - 运动规划、轨迹控制、多智能体协同
- 🌾 **精准农业** - 高通量表型、产量预测、智能装备
- 🦾 **多智能体系统** - 集群控制、协同作业、自主导航

## 👥 团队成员

| 类别 | 数量 | 详情 |
|------|------|------|
| 导师（指导教师） | 3 | 教授、讲师 |
| 博士研究生 | 10 | 2022-2025级 |
| 硕士研究生 | 20+ | 2024-2026级 |
| 已毕业校友 | 60+ | 进入学术界和产业界 |

**[查看完整成员列表 →](https://smart-ag.github.io/members/)**

## 🏆 荣誉与成就

### 学术认可

- 🌟 **World Top 2% Scientists** - 2024, 2025年度（傅隆生教授）
- 🎖️ **爱思唯尔中国高被引学者** - 2024, 2025, 2026年度
- 📊 **中国知网高被引学者 TOP 1%** - 2024, 2025年度

### 竞赛获奖

- 🥇 **全国大学生智能农业装备创新大赛** - 国家级一等奖、二等奖
- 🎓 **中国研究生机器人创新设计大赛** - 多项获奖

**[查看全部奖项 →](https://smart-ag.github.io/awards/)**

## 📚 研究成果

### 发表论文

- **100+** 篇学术论文（SCI/EI收录）
- 发表在 *IEEE Transactions*, *Computers and Electronics in Agriculture*, *Pattern Recognition* 等顶级期刊

**[浏览论文库 →](https://smart-ag.github.io/publications/)**

### 研究项目

- **20+** 个在研和已完成项目
- 涵盖基础研究、应用研究、成果转化等多个阶段

**[查看项目详情 →](https://smart-ag.github.io/projects/)**

### 学术活动

- 定期举办**学术报告会**和**研讨会**
- 邀请国内外知名专家做学术报告
- 参加国际学术会议展示研究成果

**[学术报告 →](https://smart-ag.github.io/scholarly%20seminars/)**

## 🌐 网站功能特性

- 📱 **响应式设计** - 完美适配手机、平板、电脑
- 🌙 **亮/暗模式** - 自动检测系统偏好并支持手动切换
- 📄 **学术出版展示** - 自动从BibTeX生成论文列表
- 👥 **成员管理系统** - 展示导师、学生、校友信息
- 🏆 **获奖成就展示** - 分类展示各类奖项和荣誉
- 📊 **项目展示** - 响应式网格展示研究项目
- 🎓 **活动记录** - 记录学术报告、会议参展等活动

## 🚀 快速开始

### 系统要求

- [Ruby](https://www.ruby-lang.org/en/) >= 2.7
- [Jekyll](https://jekyllrb.com/) >= 4.2
- [Bundler](https://bundler.io/)

### 本地运行

```bash
# 克隆仓库
git clone https://github.com/Smart-Ag/Smart-Ag.github.io.git
cd Smart-Ag.github.io

# 安装依赖
bundle install

# 运行开发服务器
bundle exec jekyll serve
```

网站将在 `http://localhost:4000` 访问。

### 生产部署

本网站托管在 [GitHub Pages](https://pages.github.com/)，推送到 GitHub 后会自动通过 GitHub Actions 部署。详见 [INSTALL.md](INSTALL.md)。

## 📝 项目结构

```
.
├── _pages/                  # 主页面（关于、成员、论文、项目等）
├── _projects/               # 研究项目和学术会议
├── _activities/             # 学术活动和学术报告
├── _bibliography/           # BibTeX 论文数据库
├── _data/                   # 数据文件
│   ├── members.yml          # 成员信息
│   ├── awards.yml           # 奖项与荣誉
│   ├── announcements.yml    # 公告信息
│   └── carousel.yml         # 首页幻灯片
├── _layouts/                # Jekyll 页面布局
├── _includes/               # 可复用的HTML组件
├── _sass/                   # SCSS样式文件
├── assets/                  # 静态资源
│   ├── img/                 # 图片和照片
│   ├── pdf/                 # 论文PDF文件
│   ├── css/                 # CSS样式表
│   └── js/                  # JavaScript文件
└── _config.yml              # Jekyll 配置文件
```

## ✏️ 如何更新网站

### 更新成员信息

编辑 [`_data/members.yml`](_data/members.yml)：

```yaml
current:
  - year: "2025级"
    name: "您的名字"
    degree: "博士研究生"
    photo: "/assets/img/members/your_photo.jpg"
    research: "研究方向"
```

### 添加论文

编辑 [`_bibliography/papers.bib`](_bibliography/papers.bib)，使用 BibTeX 格式添加新论文：

```bibtex
@article{your_paper_2026,
  title={Your Paper Title},
  author={Author Name and Others},
  journal={Journal Name},
  year={2026},
  pdf={your_paper.pdf}
}
```

### 发布新项目

在 [`_projects/`](_projects/) 目录创建新的 Markdown 文件：

```markdown
---
layout: page
title: Project Title
description: Project description
category: Projects
---

Project content...
```

### 记录学术活动

在 [`_activities/`](_activities/) 目录创建新的 Markdown 文件：

```markdown
---
layout: page
title: Activity Title
date: 2026-06-29
category: Presentations
---

Activity content...
```

详见 [CUSTOMIZE.md](CUSTOMIZE.md)。

## 🔧 技术栈

| 技术 | 说明 |
|------|------|
| [Jekyll](https://jekyllrb.com/) | 静态网站生成器 |
| [Bootstrap](https://getbootstrap.com/) | 响应式UI框架 |
| [MathJax](https://www.mathjax.org/) | 数学公式渲染 |
| [Highlight.js](https://highlightjs.org/) | 代码高亮 |
| [Liquid](https://shopify.github.io/liquid/) | 模板语言 |
| [GitHub Pages](https://pages.github.com/) | 网站托管 |

## 📧 联系方式

### 实验室主任

**傅隆生 (Fu Longsheng)**

- 📧 邮箱: fulsh@nwafu.edu.cn
- 🏫 机构: 西北农林科技大学
- 📱 电话: 可通过官网查询

### 学生招生

欢迎对农业机器人、计算机视觉、智能控制感兴趣的学生申报！

- 🎓 **博士研究生** - 欢迎推荐免试生和社会考生
- 🎓 **硕士研究生** - 欢迎学术型和专业型考生
- 📧 联系: fulsh@nwafu.edu.cn

## 📜 许可证

本网站代码基于 [MIT License](LICENSE) 开源。

本网站基于 [al-folio](https://github.com/alshedivat/al-folio) 主题开发。

---

**网站**: https://smart-ag.github.io/  
**GitHub**: https://github.com/Smart-Ag/  
**最后更新**: 2026年6月29日

## 🔧 维护和更新

### 定期任务

- 🔄 **每周** - 更新成员信息、论文数据库
- 📝 **活动后** - 记录学术报告和学术活动
- 🎓 **每学期** - 更新成员学位、入学年级
- 🏆 **获奖后** - 添加新的奖项和荣誉

### 自动化工作流

本项目使用 GitHub Actions 实现以下自动化：

- 📊 **代码质量检查** - 使用 Prettier 检查代码风格
- 🔗 **死链检测** - 使用 lychee 检查网站链接
- 🚀 **自动部署** - 推送到 GitHub 后自动部署到 GitHub Pages

查看 [.github/workflows/](.github/workflows/) 了解更多详情。

## 📖 文档

- 📚 [INSTALL.md](INSTALL.md) - 安装和部署指南
- 🎨 [CUSTOMIZE.md](CUSTOMIZE.md) - 网站自定义指南
- ❓ [FAQ.md](FAQ.md) - 常见问题
- 🤝 [CONTRIBUTING.md](CONTRIBUTING.md) - 贡献指南

## 🤝 贡献

我们欢迎各种形式的贡献！

### 贡献指南

1. **提交问题** - 发现bug或有改进建议？提交 Issue
2. **提交代码** - Fork 本仓库，创建分支，提交 Pull Request
3. **改进文档** - 帮助我们改进文档和说明
4. **反馈建议** - 告诉我们如何改进网站

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## 📞 获取帮助

- 📧 **邮件**: fulsh@nwafu.edu.cn
- 💬 **GitHub Issues**: [提交问题](https://github.com/Smart-Ag/Smart-Ag.github.io/issues)
- 🌐 **网站**: https://smart-ag.github.io/

## 📜 许可证

本项目基于 [MIT License](LICENSE) 开源。

### 致谢

本网站基于 [al-folio](https://github.com/alshedivat/al-folio) 主题开发，感谢原项目作者和贡献者。

---

<div align="center">

**Smart Agrobot Lab** © 2026  
Northwest A&F University

[🌐 访问网站](https://smart-ag.github.io/) | [🐙 GitHub](https://github.com/Smart-Ag) | [📧 联系我们](mailto:fulsh@nwafu.edu.cn)

</div>
