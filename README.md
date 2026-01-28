# 东南大学硕士毕业论文 Latex 模板

本仓库是基于garbagecodes的 [SEU-master-thesis-template
](https://github.com/garbagecodes/SEU-master-thesis-template)  修改而来。

## 模板修改次序

TouchFishPioneer -->  Reanon

TouchFishPioneer  +  Reanon  -->  levitate-qian（2024）  --> garbagecodes（2025） -->  本模板 （2026）

TouchFishPioneer: [SEU-master-thesis](https://github.com/TouchFishPioneer/SEU-master-thesis)

Reanon: [SEUThesisLatexTemplate](https://github.com/Reanon/SEUThesisLatexTemplate)

levitate-qian: [SEUThesisLatexTemplate-Levitate](https://levitate.lanzoub.com/iRmnq2j8wcnc)    
[LaTeX札记（七）：硕士学位论文相关](https://levitate-qian.github.io/2024/12/28/latex-note-07/)

garbagecodes: [SEU-master-thesis-template
](https://github.com/garbagecodes/SEU-master-thesis-template)

## 本模板修改内容

- 对于每一章第一页、摘要、致谢、作者简介的页眉进行补全。
- 新提供去掉空白页的选项，\seuDoublePageMode{ }，print: 印刷版，全书强制插空白页, digital: 电子版，仅正文强制插空白页。
- 修复学硕模板中A4小封面，缺少研究方向字样、日期被挤到下一页等问题。
- 新提供了一个选项，\seuTocChapterVSpaceOff，可以控制目录中章节之间是否需要间隙，开启则与Word模板一致。


## 使用攻略
不建议在Windows下自建环境编译，字体可能会不一致，本项目无法提供相关支持，请查阅本项目修改的原项目。

### Overleaf及Mac
编译器请选XeLaTeX，主文件选择main.tex，如遇编译时间超时，可以先使用Draft快速编译再使用常规编译。

详见Reanon: [SEUThesisLatexTemplate](https://github.com/Reanon/SEUThesisLatexTemplate) 或 docs/README-src.md或docs/README.pdf

Overleaf现在超时编译很严重，可以考虑使用[texpage](https://www.texpage.com)，基本操作与Overleaf一致。

### Windows

参考CSDN[Latex和Vscode安装和配置](https://blog.csdn.net/bulletstart/article/details/142502912)或[VScode配置LaTex编辑](https://blog.csdn.net/weixin_55988068/article/details/138716818)

需执行脚本`make.bat`



