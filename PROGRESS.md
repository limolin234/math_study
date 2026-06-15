# Progress

## 2026-05-27

- 建立数学学习笔记项目：`~/Myproject2/math_study`。
- 确定维护方式：对话中学习，重要公式和结构化总结写入 Markdown，用 VS Code 渲染 LaTeX。
- 当前采用“分支目录 + 小主题 Markdown”的结构：微积分、线性代数、抽象代数、实分析、概率论、复分析、杂项。
- 已整理主题：
  - `complex_trig.md`：复数输入下的三角函数。
  - `calculus/integration_quadratic_trig_complex.md`：积分、二次式、三角/双曲/复数结构总结。

## 后续维护原则

- 重要公式进入 Markdown，不依赖聊天上下文。
- 每个小主题单独成文，便于 VS Code 预览、搜索和归档。
- 若一个主题跨多个分支，先放在最主要分支；必要时在其他分支 README 中交叉链接。
- 学习时优先保留“结构解释 + 典型例题 + 最小记忆包”。
- 修订 `calculus/integration_quadratic_trig_complex.md`：删去第 3 题的对称性/复分析解释，改为详细说明交换积分顺序后内层积分 `K(s)` 的万能代换计算。
- 新增 `tmp.md` 作为临时黑板：Codex 对话用于交流，公式和临时推导写入 `tmp.md`，稳定后再整理到正式 Markdown。
- `tmp.md` 黑板更新：补充 `tanh` 与 `artanh` 的定义、反解推导，以及为什么 `1/(1-x^2)` 的积分产生 `artanh`。
- 记录新规则：Codex 对话框只用普通文字，不写 LaTeX 公式推导；公式和推导统一写入 `tmp.md`，用户用 VS Code 渲染查看。
- `tmp.md` 黑板更新：整理三角函数、双曲函数、反三角/反双曲函数、相关积分表，以及有理函数积分的部分分式拆分和代入法复习。
- `tmp.md` 黑板更新：解释代数基本定理、实系数多项式的一次/不可约二次分解，与“高次方程是否能用二次公式求解”的区别。
- `tmp.md` 黑板追加：整理积分表中的正负号问题，结合三角函数、双曲函数、反函数和平方差形式说明符号来源与检查方法。
- `tmp.md` 黑板追加：切换到概率论，解释经验分布、经验分布函数、与均匀分布的区别以及其作为真实分布近似的意义。
- 整理 `tmp.md`：将积分表/正负号/有理函数积分整理到 `calculus/integration_table_signs_rational_functions.md`，将经验分布相关内容整理到 `probability/empirical_distribution.md`，并清空黑板。

- tmp.md 黑板追加：继续概率论，整理随机变量、分布函数、离散型/连续型、PMF 与 PDF 的区别。

- tmp.md 黑板追加：参考作业 11.3，整理 Beta/Gamma 函数定义、常见公式、三角积分、Gamma 型积分、Beta 型积分及作业题计算。

- tmp.md 黑板追加：参考作业 12.1，整理二重积分性质、比较大小、交换积分次序、矩形/一般区域积分、体积和不等式证明。
