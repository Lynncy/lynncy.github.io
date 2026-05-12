---
title: 'My recent note-taking workflow for single articles using Obsidian, Zotero, and Claude code'
layout: single
date: 2026-05-12
permalink: /posts/2026/05/12blog-post-1/
toc: true          # 触发原生 TOC
toc_sticky: true   # 触发原生 Sticky 悬浮
tags:
  - obsidian
  - zotero
  - claudecode
---

{% include toc %}


# 1 主要流程

上个月见到皋老师，被种草了obsidian+zotero记单篇笔记的方法，感觉超级方便啊！结合导导的教程和社媒经验帖，摸索调整后形成了适合自己的流程_(:з」∠)_

我的需求大致如下（如果一致可以参考！）：
1. 贫苦的zotero用户（勉强充了2G但根本不够啊😿）我不太习惯在zotero里看论文，也懒得标多颜色highlight。zotero对我而言的主要用途是自动规范citation format，提供bibtex和论文的一些meta data。
2. 我有一个固定的内容模板（按常见的human factors论文分成了4类），里面有些内容是比较固定的，AI完全可以整理，但是需要我核查、以及需要明确链接到pdf中具体的位置，还有些评论内容是需要自己填的。即我需要：AI一口气按我模板总结->我调整+补充。
3. 我不太需要跟AI迭代着看论文记笔记（需要迭代的朋友可以看看llm-for-zotero之类工具）。
4. 可能过段时间需要整理多个笔记，比如按不同维度（例如归属项目、主题、方法等）来归类。

我的笔记模板大致包括三类内容：
1. 文献bib等meta data
2. 常规研究过程（研究问题、重要概念、方法结果等）
3. 自己的瑞平（可以借鉴的、想吐槽的、受启发的新内容等）

内容1和2主要是为了今后自己或AI搜索方便而整理的，<mark style="background:#fff88f">写下内容3的过程才是对自己理解论文最有帮助的一环</mark>……所以我内容1的bib主要靠zotero导入，内容2用AI生成+我审核，内容3自己写。操作步骤如下：
1. **准备**：常规地把看摘要觉得有用的文献pdf存在自己习惯的位置，并在zotero加一条记录存好meta data。
2. **创建一个自动带这篇文章bib的笔记毛坯房**：需要开着zotero插件`Better BibTex for Zotero`以及obsidian插件`Zotero Integration`，用提前设置好的一个`Import Format`功能，能按模板一键创建，导入zotero里存的meta data。
3. **AI先总结**：用顺手的AI coding工具（我现在用的是VSCode的Claude code + deepseek-v4-pro，全球性价比之王！！只能处理文本没有多模态，但是够用了！），让它参考我之前手动创建的笔记，基于pdf文件把毛坯房的固定信息填好。
4. **手动调整+评论**：我直接在obsidian中开左右两个窗口，一个是笔记，另一个用`PDF++`这个插件查看pdf，highlight或者复制的内容，贴到笔记时会创建pdf和笔记之间的链接。最后再写点感悟。
5. **未来的多篇总结**：有很多论文之后，可以另开笔记，用obsidian 的`dataview`从不同角度总结。


# 2 细节
## 2.1 关于自动部分（创建毛坯房+AI总结）

### 2.1.1 模板设置

参考皋老师的模板，不过区别在（1）我没有zotero导入的批注，（2）中间常规研究过程按文献类别区分，（3）按需设置了笔记属性meta data，以及后续在汇总多篇文献时，需要`dataview`抓哪些信息。

<img src='/images/post_attachment/e6f0aabc-b8c1-482f-909e-1a2461f13a26.png'/>


我的模板中有关常规研究过程的部分（主要是方法和结果）分了4类研究类型，选用以下不同的模板。这部分AI确实可以自己选择合适类型，初步填写。

<img src='/images/post_attachment/屏幕截图 2026-05-12 125501.png'/>


### 2.1.2 Zotero Integration的设置
zotero插件`Better BibTex for Zotero`只要装上就完事了，开着就行。但obsidian插件`Zotero Integration`需要设置一下。这个插件的导入设置里，可以增加2类导入：（1）在citation formats里，可以设置如何在正文里cite论文（类似于zotero word插件），（2）在import formats里，可以设置如何导入论文的bib数据。这里需要用第二类，需要点`Add Import Format`来新建一个导入笔记的快捷方式（基本copy的皋老师的设置……只不过命名按自己习惯调了调、template换成自己的）。

<img src='/images/post_attachment/34ec3af0-c7ee-4c48-81b3-c905c9472d69.png'/>


创建好之后，就可以在笔记中按`ctrl + p`（win用户），搜“Zotero Integration: CreatLitreNote”，回车后就会蹦出zotero选择文献的bar。选好后就会自动创建出一个基本bib填好的毛坯房啦。

然后，就可以去claude code让它参考我之前手动创建的笔记，基于pdf文件把笔记填好（瑞平部分也可以让它写，因为有时他说的点我可能没关注到也很有启发；觉得ai写得没用可以删掉）。

## 2.2 关于手动调整+评论

以下截图展示在obsidian中开左右两个窗口的样子。`PDF++`可以highlight或者复制内容，贴到笔记的同时可以创建pdf和笔记之间的链接。双向链接是伟大的发明！查找起来很方便！

<img src='/images/post_attachment/Pasted image 20260512092428.png'/>



