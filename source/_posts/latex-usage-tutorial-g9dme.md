---
title: Latex使用教程
date: '2026-04-19 12:29:46'
updated: '2026-04-29 17:04:21'
permalink: /post/latex-usage-tutorial-g9dme.html
comments: true
toc: true
---



# Latex使用教程

# 导言区

导入宏包  
\usepackage{booktabs}(三线表}  
\usepackage{amsmath,amsfonts,amsthm}%数学公式  
\usepackage{bm}  
\usepackage{mathrsfs}

\\maketitle 把信息栏的内容体现在正文中  
正文开启新的段落之后，首段会自动缩进，空行表示新的段落的开始  
\\textbf{加粗}  
\\textit{斜体}  
\\underline{}  
\section表示一个大节1  
\subsection{}1.1靠左对齐  
\subsection{}1.2  
\subsubsection{}1.1.1

目录  
\newpage开启新的一页  
\tableofcontents(自动生成，根据你的文件大纲生成）

列表  
建立一个列表的环境  
\begin{enumerate} #有序列表  
	\item a  
	\item b  
	\item c  
\end{enumerate}

\begin{itemize}#无序列表  
	\item a  
	\item b  
	\item c  
\end{itemize}

## 插入图片

\begin(figure}【h】  
	\centering将图片居中  
	\includegraphics【width=0.5\textwidth(图片占页面的比例）】图片文件  
	\caption{caption}图片标题  
\end{figure}

并排图片(本质将页面分割）  
新建目录专门放入图片

<span data-type="text" style="color: var(--b3-font-color1);">\begin{figure}</span>  
	<span data-type="text" style="color: var(--b3-font-color1);">\begin{minipage}{0.48\textwidth}将页面分割</span>  
	\centering将图片居中  
	\includegraphics【width=0.5\textwidth(图片占页面的比例）】{figure/图片文件}  
	\caption{caption}图片标题  
	<span data-type="text" style="color: var(--b3-font-color1);">\end{minipage}</span>  
	<span data-type="text" style="color: var(--b3-font-color1);">\begin{minipage}{0.48\textwidth}将页面分割</span>  
	\centering将图片居中  
	\includegraphics【width=0.5\textwidth(图片占页面的比例）】{figure/图片文件}  
	\caption{caption}图片标题  
	<span data-type="text" style="color: var(--b3-font-color1);">\end{minipage}</span>  
<span data-type="text" style="color: var(--b3-font-color1);">\end{figure}</span>

## 插入表格

  
\begin{table}[h]  
	\centering  
	\begin{tabular}{c|c\} c表示添加新的列  
	\hline添加横线  
 |表示在列中添加束线  
	& 表示单元格的分割 \\\表示换行  
**三线表(记得导入宏包）**

```undefined
\begin(table)	
	\centering
	\begin{tabular}{c|c}
	\toprule
		物理符号&  物理意义 \\
	\midrule
	\bottomrule
	\end{tabular}
	\caption{caption}
	\label
\end{table}
```

## 空白代码

\hspace{}设置空格的大小  
\qquad  
\qquad\qquad物理符号\qquad\qquad\qquad&\qquad\qquad  物理意义\qquad\qquad\qquad \\\

将表格转化为latex代码形式表格  
[Create LaTeX tables online – TablesGenerator.com](https://www.tablesgenerator.com/)

## 数学公式

环境：独占一行的数学公式，叫做外显公式  
	在语句里面的数学公式，叫做内显公式  
行内公式  
在公式左右放入$符号，比较美观\dispalystyle  
外显公式  

```undefined
\begin{equation*}
	a+b=B+c\..
\end{equation*}
```

‍
