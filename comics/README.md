# 🎬 程序员英语漫画剧场 · 霓虹墨 Neon Ink

> 把程序员学英语的关键认知画成四格漫画：每话一幅 **1200×840 SVG 原画** + 一篇**讲解 MD**（剧情回顾 / 知识点拆解 / 坑点清单 / 自测题）。
> 视觉体系：深墨底 + 霓虹青/紫/品红 + 斜切光楔；三角色——**像素酱**（提问担当）、**标签君**（行动派）、**码叔**（教授总结）。规范见 [style-guide.md](./style-guide.md)，定妆稿见 [samples/character-sheet.svg](./samples/character-sheet.svg)。

## 📖 一键阅读（整合阅读器）

打开 <a href="/comics/index.html" target="_blank" rel="noopener">index.html</a>（需经本地 HTTP 服务访问，命令见文末「本地预览」），在封面点击「一键打开完整漫画」即可：

- 按 `manifest.json` 组织全部话目（SVG 内联，矢量无损缩放）；
- **翻页 / 长卷双模式**、讲解抽屉、阅读进度记忆、章节导航、话目网格搜索——详见阅读器封面说明。

## 建议读法

1. 先看原画 SVG，跟着剧情把概念"看见"；
2. 再读同 slug 的讲解 MD，把每一格落成方法与例句；
3. 最后点开"对应正文"链接，回到教程主线深读并完成练习。

## 目录

| 话 | 主题 | 原画 | 讲解 | 对应正文 |
| ---- | ---- | ---- | ---- | ---- |
| EP.01 | 技术英语不是学校英语 | [SVG](./EP.01-tech-english-not-school-english.svg) | [MD](./EP.01-tech-english-not-school-english.md) | [01 核心词汇体系](../01-core-vocabulary.md) |

## 话目规划（Roadmap）

以下话目已规划、待绘制，完成一话即从规划表移入上方目录并登记 `manifest.json`：

| 话 | 主题 | 对应正文 |
| ---- | ---- | ---- |
| EP.02 | 被动语态是文档之魂 | 02 高频句式与语法 |
| EP.03 | 祈使句占领 README | 02 高频句式与语法 |
| EP.04 | API 文档速读法 | 03 技术文档速读 |
| EP.05 | Issue 里的人在说啥 | 03 技术文档速读 |
| EP.06 | Commit Message 的规矩 | 04 技术写作实战 |
| EP.07 | PR 描述三件套 | 04 技术写作实战 |
| EP.08 | Review 评论的艺术 | 04 技术写作实战 |
| EP.09 | 邮件与 IM 的分寸 | 05 职场沟通表达 |
| EP.10 | 易错表达红黑榜 | 06 附录与资源 |

## 目录结构

```
comics/
├── index.html                # 整合阅读器（翻页/长卷双模式 + 讲解抽屉 + 进度记忆）
├── style-guide.md            # 霓虹墨风格规范（唯一视觉标准）
├── samples/
│   └── character-sheet.svg   # 三角色定妆稿 v2
├── manifest.json             # 话目清单（校验脚本的依据）
├── check-comics.mjs          # 校验：manifest 一致性 + SVG 良构 + 文本溢出启发式
├── EP.NN-*.svg               # 每话原画（1200×840 四格）
└── EP.NN-*.md                # 每话讲解（剧情/拆解/坑点/自测）
```

## 本地预览

```bash
cd programmer-english-guide
python3 -m http.server 8899
# 整合阅读器（推荐）：http://127.0.0.1:8899/comics/index.html
# 单话原画直开：http://127.0.0.1:8899/comics/EP.01-tech-english-not-school-english.svg
```

> 阅读器依赖 `fetch` 合并资源，`file://` 直开会被浏览器拦截，页面会给出上述启动提示。

## 校验

```bash
node comics/check-comics.mjs
```
