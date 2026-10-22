# EP.01 技术英语不是学校英语

> 对应正文：[01-core-vocabulary.md](../01-core-vocabulary.md)（1.1 场景导入 / 1.2 方法论 / 1.4 调试报错词组 / 1.6 中式英语常见错误）

## 剧情回顾

- **第 1 格**：标签君读 React 文档，把 `render` 当成"表演"、`cleanup` 当成"大扫除"——每个词都查过字典，整句意思却拼不起来。
- **第 2 格**：码叔点破症结：单词要按**词块**记。三个高频词块芯片：`is deprecated, use X instead` / `mutates the array in place` / `Cannot read properties of ...`。
- **第 3 格**：像素酱拿一条真实 `TypeError` 报错做实证：错误类型 → 发生了什么 → 在哪一行，三段拆开就能定位。
- **第 4 格**：码叔结案——扔掉四六级词表，换成真实语料词块；三条坑点当场示众。

## 知识点拆解

### 第 1 格 · 日常义项为什么会失效

- `render` 的日常义项是"表演/给予"，技术义项是"渲染"（组件输出 UI）；
- `cleanup` 日常指"大扫除"，React 里指 Effect 的清理函数；
- 技术阅读的第一课：**遇到熟词生义，以技术语境为准重建义项**，而不是硬套字典第一条。

### 第 2 格 · 词块（chunk）为什么比单词高效

- 孤立背 `deprecate = 废弃`，读句子时还要现场组装语法；
- 整块记 `This API is deprecated, use X instead.`，读到时整句理解、写作时整句调用；
- 统计主流开源文档，约 500 个高频词块覆盖 90% 内容——这就是[第 1 章](../01-core-vocabulary.md)词表的来源。

### 第 3 格 · 报错三段式拆解法

任何一条运行时报错都可以拆成三段：

1. **错误类型**：`TypeError` / `ReferenceError` / `SyntaxError`；
2. **发生了什么**：`Cannot read properties of undefined (reading 'map')` —— 在 `undefined` 上读了 `map`；
3. **在哪**：栈帧 `at UserList (UserList.jsx:24:18)` —— 文件、行、列。

三段读完，修复方向自然浮现：找到第 24 行调用 `.map()` 的变量，查它为什么是 `undefined`。

### 第 4 格 · 换一套学法

- 词汇来源换成真实语料：报错信息、官方文档、Issue/PR 评论；
- 记忆单位换成词块：带着搭配和句式一起记；
- 检验标准换成输出：能写进 Commit message 和 Review 评论，才算真正掌握。

## 坑点清单

> 🔗 正文对照：[《1.6 中式英语常见错误》](../01-core-vocabulary.md#_1-6-中式英语常见错误)

1. 背四六级/托福词表应付技术阅读——词频错位，`render` 背了"表演"反而误导；
2. 长句逐词翻译——正确顺序是先找词块和句式骨架，再填细节；
3. 用 `very` / `very much` 修饰动词——`I very like this API.` ❌，应说 `I really like this API.`；
4. 把中式客套搬进 Review——`Please kindly help me...` 不如 `Could you take a look? Thanks!`。

## 自测 3 题（含答案）

1. 为什么"每个词都认识"却读不懂技术文档？——**技术语境下单词义项与日常义项不同，且理解单位应是词块而非孤词**。
2. `Cannot read properties of undefined (reading 'map')` 的修复方向？——**某变量是 undefined 却被调用了 `.map()`，沿栈帧定位后检查该变量为何不是数组**。
3. `deprecated` 和 `removed` 的区别？——**deprecated 是"仍可用但不要再用于新代码"，removed 是"已删除"，升级依赖时必须区分**。
