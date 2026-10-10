# PRL-like LaTeX 模板

基于 APS **REVTeX 4.2** 的 Physical Review Letters 风格双栏模板，并加入中文支持与常用排版设置，适合撰写类 PRL 版式的中文学术短文、报告或预印本。

## 主要特性

- 双栏排版（`aps,prl,reprint`）
- `ctex` 中文支持
- 自定义页眉页脚（`fancyhdr`）
- 公式、图片、三线表示例
- BibTeX 参考文献（`ref.bib`）

## 文件说明

| 文件 | 说明 |
|------|------|
| `PRL_templates.tex` | 主文档 |
| `ref.bib` | 参考文献数据库 |
| `picture_templates.jpg` | 示例图片 |
| `PRL_templates.pdf` | 编译结果示例 |

## 使用方法

1. 复制本文件夹，或直接编辑 `PRL_templates.tex`。
2. 修改文首信息：
   - `\title{...}` 标题
   - `\author{...}` 作者
   - `\affiliation{...}` 单位
   - `abstract` 摘要
3. 按需改写各 `\section`，替换公式、图表与文字。
4. 在 `ref.bib` 中添加文献，正文用 `\cite{key}` 引用。
5. 页眉文字在 `\fancyhead[C]{...}` 中修改。

### 插图

跨双栏宽图使用 `figure*`，例如：

```latex
\begin{figure*}[htbp]
  \centering
  \includegraphics[height=4cm,keepaspectratio]{your_figure.jpg}
  \caption{图注}
  \label{fig:example}
\end{figure*}
```

### 表格

三线表示例见主文件中的 `booktabs` 用法（`\toprule` / `\midrule` / `\bottomrule`）。

## 编译

推荐使用 **XeLaTeX**（中文更稳妥），完整流程：

```bash
xelatex PRL_templates.tex
bibtex PRL_templates
xelatex PRL_templates.tex
xelatex PRL_templates.tex
```

也可在 TeXstudio、Overleaf 等编辑器中将编译引擎设为 XeLaTeX，并启用 BibTeX。

## 依赖

需已安装 TeX Live / MiKTeX，并包含：

- `revtex4-2`
- `ctex`
- `amsmath`、`graphicx`、`booktabs`、`fancyhdr`、`geometry` 等常用宏包

## 版式选项提示

主文件中的文档类：

```latex
\documentclass[aps,prl,reprint,groupedaddress]{revtex4-2}
```

- `reprint`：双栏最终版式
- 可改为 `preprint` 得到单栏预印本样式
- 期刊选项还可换成 `pra`、`prb` 等


## 交流和问题
如果遇到关于本文档的任何问题，请联系herman060330@gmail.com

欢饮批评指正以及交流讨论！