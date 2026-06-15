# agent.md

这个文件用于记录 `math_study` 项目的当前维护方式和进度入口。详细协作规则见 `AGENT.md`。

## 当前工作流

- 我们在 Codex 对话中讨论数学问题。
- 重要公式、推导、判断规则写入 Markdown。
- 用户用 VS Code 查看和渲染 Markdown/LaTeX。
- 目录天然作为归档，不依赖模型长期上下文。

## 当前结构

- `README.md`：总目录。
- `PROGRESS.md`：进度记录。
- `AGENT.md`：项目级维护规则。
- `calculus/`：微积分与积分技巧。
- `linear_algebra/`：线性代数。
- `abstract_algebra/`：抽象代数。
- `real_analysis/`：实分析。
- `probability/`：概率论。
- `complex_analysis/`：复分析。
- `notes/`：暂时不能归类的笔记。

## 当前已整理主题

- `complex_trig.md`：复数输入下的三角函数。
- `calculus/integration_quadratic_trig_complex.md`：积分、二次式、三角/双曲/复数结构总结。

## 本次新增核心内容

本次把以下主题整理为正式 Markdown：

- Poisson 核型对数积分：
  \[
  \int_0^\pi \ln(1-2d\cos x+d^2)\,dx=0,\quad |d|<1.
  \]
- 对数二次三角积分：
  \[
  \int_0^{\pi/2}\ln(a^2\sin^2x+b^2\cos^2x)\,dx
  =\pi\ln\frac{a+b}{2}.
  \]
- 三角换元、万能代换、二次式判别式与积分函数类型。
- \(\ln\)、\(\arctan\)、三角函数、双曲函数、复对数之间的统一结构。

## 下次继续时

优先读取：

1. `README.md`
2. `PROGRESS.md`
3. `AGENT.md`
4. 当前讨论分支下的对应 Markdown
## 黑板约定

- `tmp.md` 是临时黑板。
- 对话中不方便渲染的公式、推导、草稿优先写到 `tmp.md`。
- Codex 对话框只保留简短说明和确认。
- 推导稳定后，再从 `tmp.md` 整理进正式主题 Markdown。

## 对话与黑板规则

- Codex 对话框只使用普通文字说明，不在对话框里写 LaTeX 公式推导。
- 所有公式、推导、计算过程、临时草稿优先写入 `tmp.md`。
- 用户在 VS Code 中查看和渲染 `tmp.md`。
- 对话框只说类似“已写到黑板”“看 tmp.md 的某一节”“这里关键是某个思路”。
- 推导稳定后，再从 `tmp.md` 整理进正式主题 Markdown。

## tmp.md 追加规则

- `tmp.md` 默认使用追加模式，不轻易覆盖旧内容。
- 新问题、新推导、新例子追加到文件末尾。
- 每次追加使用清楚的二级标题或分隔线，方便之后整体整理。
- 如果 `tmp.md` 变长，可以先追加“待整理索引”，再分批搬运到正式主题文件。
- 只有用户明确要求“清空黑板”“重写 tmp.md”时，才覆盖或清空 `tmp.md`。
- 从 `tmp.md` 整理到正式 Markdown 后，可以保留原黑板记录，或按用户要求归档/清空。
