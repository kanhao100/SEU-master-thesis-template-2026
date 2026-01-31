# 东南大学硕士毕业论文 Latex 模板 2026

本仓库是基于garbagecodes的 [SEU-master-thesis-template
](https://github.com/garbagecodes/SEU-master-thesis-template)  修改而来。
本仓库针对一些历史遗留问题进行了修复，同时对学术博士论文进行了一定的支持。本仓库的特色是提供了各种接口可供同学们选择使用，而不是覆盖式修改。

## 模板修改次序
基于上一个版本提供的修改次序，如有遗漏尽请谅解。

zhimengfan1990 --> TouchFishPioneer -->  Reanon -->  levitate-qian（2024）  --> garbagecodes（2025） -->  本模板 （2026）

zhimengfan1990: [seuthesix](https://github.com/zhimengfan1990/seuthesix)

TouchFishPioneer: [SEU-master-thesis](https://github.com/TouchFishPioneer/SEU-master-thesis)

Reanon: [SEUThesisLatexTemplate](https://github.com/Reanon/SEUThesisLatexTemplate)

levitate-qian: [SEUThesisLatexTemplate-Levitate](https://levitate.lanzoub.com/iRmnq2j8wcnc)    
[LaTeX札记（七）：硕士学位论文相关](https://levitate-qian.github.io/2024/12/28/latex-note-07/)

garbagecodes: [SEU-master-thesis-template](https://github.com/garbagecodes/SEU-master-thesis-template)

## 本模板修改内容

### 正文部分
- 对于正文每一章首页、摘要、致谢、作者简介的页眉进行补全。[Issue#2](https://github.com/TouchFishPioneer/SEU-master-thesis/issues/2)
- 新提供去掉空白页的选项，\seuDoublePageMode{ }，[Issue#14](https://github.com/TouchFishPioneer/SEU-master-thesis/issues/14)
  - print   : 印刷版，全书强制各章节首页保持奇数页（会插空白页），因为前面的封面页较多，所以看起来很多空白页，原来的模板默认选项
  - digital : 电子版，仅正文强制各章节首页保持奇数页（会插空白页），建议的选项，本模板默认选项
  - blind1  : 盲审版1，正文不插空白页但跳页（章节首页保持奇数页）
  - blind2  : 盲审版2，正文不插空白页也不跳页 （这会导致章节首页的页眉可能出现"东南大学硕士学位论文"而不是章节标题）
- 修复了学硕模板中A4小封面中缺少研究方向字样、日期被挤到下一页等问题。请见[2024年12月研究生院下发的写作指南中](docs/东南大学研究生学位论文写作指南-1203V4.pdf)的论文封面参考模板。
- 新提供了一个选项，\seuTocAndListVSpaceOff，可以控制目录中章节之间是否需要间隙，开启则与Word模板一致，本模板默认开启。
- 修复了pdf书签中“目录”跳转错误 [Issue#19](https://github.com/TouchFishPioneer/SEU-master-thesis/issues/19)
- 添加了学术博士的支持，但不保证格式正确性，请自行检查核对。
- 添加了参数bookmarksnumbered，可以控制书签中是否出现章/节编号，开启则与Word模板一致，本模板默认开启。
- 新增 `chapters/nomenclature.tex` 集中存放术语与符号表，方便修改。
- 封面大标题字号从二号改为一号，和word模板一致；封面样式修改，对于学硕模板进行了精细化调整，但同时也支持专硕封面；修复了大封面和小封面两行断行位置不一样的问题。
- 如果发现其它格式问题，请提issue，本仓库提供技术支持到2026年6月。

### 参考文献部分
参考文献格式非常混乱，虽然[2024年12月研究生院下发的写作指南中](docs/东南大学研究生学位论文写作指南-1203V4.pdf)中提到按照国家标准“GB/T 7714-2015”执行，但其后面给出的具体示例却有明显不一样，给出的优秀范文中也不一样，三者均不一样。例如国标要求外文名字全大写，学位论文不区分硕士博士，给的示例却要求[博士学位论文]和[硕士学位论文]。

在garbagecodes: [SEU-master-thesis-template](https://github.com/garbagecodes/SEU-master-thesis-template)等人的模板均按照国家标准“GB/T 7714-2015”执行。但经过查阅很多过往毕业论文，很多论文既不遵照“GB/T 7714-2015”也不遵照东南大学特定格式也不遵照优秀范文的格式。

本模板将提供两个版本的参考文件格式，除了国标“GB/T 7714-2015”标准样式以外，再提供一个尽量贴合写作指南中示例的样式，在main.tex中即可控制使用哪个版本。

这部分的修改可能会比较漫长，慢慢改吧，有问题再改，先这样吧，这个版本勉强能用

TODO：增添arXiv文献参考格式
https://github.com/Reanon/SEUThesisLatexTemplate/pull/9

争议点：会议论文怎么引用

GB/T 7714-2015:

HE K, ZHANG X, REN S, et al. Deep residual learning for image recognition[C]. IEEE conference on computer vision and pattern recognition(CVPR). IEEE, 2016. 770-778.

[2024年12月研究生院下发的写作指南中](docs/东南大学研究生学位论文写作指南-1203V4.pdf)中的优秀范文的格式：

He K, Zhang X, Ren S, et al. Deep residual learning for image recognition[C]//IEEE conference on computer vision and pattern recognition(CVPR). IEEE, 2016. 770–778.

 [2024年12月研究生院下发的写作指南中](docs/东南大学研究生学位论文写作指南-1203V4.pdf)中提供的示例

He K, Zhang X, Ren S, et al. Deep residual learning for image recognition[C]. In: IEEE conference on computer vision and pattern recognition(CVPR). IEEE, 2016. 770–778.




## 使用攻略
不建议在Windows下自建环境编译，字体可能会不一致，本项目无法提供相关支持，请查阅本项目修改的原项目。

Overleaf现在超时编译很严重，请考虑使用 [texpage](https://www.texpage.com)，基本操作与Overleaf一致。

使用前建议查看main.tex的每一行代码及注释，未能支持的非电子信息专硕、专业博士论文等，请自行修改相应的部分即可。

### Overleaf及Mac
编译器请选XeLaTeX 2023以上，主文件选择main.tex，如遇编译时间超时，可以先使用Draft快速编译再使用常规编译。

详见Reanon: [SEUThesisLatexTemplate](https://github.com/Reanon/SEUThesisLatexTemplate) 或 docs/README-src.md或docs/README.pdf

### Windows

参考CSDN [Latex和Vscode安装和配置](https://blog.csdn.net/bulletstart/article/details/142502912)或 [VScode配置LaTex编辑](https://blog.csdn.net/weixin_55988068/article/details/138716818)

需执行脚本`make.bat`


### 友情链接
SEU 其它相关项目，如果有帮助请给予Star.
- 一键下载校内硕博论文库pdf： [SEU-Thesis-Download](https://github.com/kanhao100/SEU-Thesis-Download)
- 命令行进行校园网认证指南： [SEU-NET-login-Tutorial](https://github.com/kanhao100/SEU-NET-login-Tutorial)

