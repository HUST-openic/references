# EDA开发和算法设计

总结的很好的EDA汇总：

- [# 入门课程与书籍推荐之“EDA算法”](https://zhuanlan.zhihu.com/p/268633402)
- 查询集成电路的各种相关概念： [VLSI Concepts](http://www.vlsi-expert.com/)

## 目标阶段和任务计划

### 阶段一

做一个逻辑综合 + 静态时序分析工具，参考synopsys DC 和 Synopsys PT的功能和设计：

- Tauri + Vue做个SPA作为GUI。

- 开发一套symbols的读取、处理和渲染（基于WebGL）系统，详见*tech/2D3D.md*.

- 使用pybind11绑定C++语言至python从而建立命令行系统。

- 适配读取.v, .sdc文件的算法和开发。

- 沟通GUI前端和python环境的PTY问题需要解决。

- 尝试加入人工智能算法加快流程。

还有一种可能性，那就是打不过就加入，librEDA经过一年的开发，使用Rust编程出了IC后端的功能雏形，尤其是文件读取方面，不用自己写了，但是逻辑综合和时序分析功能还需要bind C++，要是感觉功能方面太卡了本学期找个机会加入算了~

### 后续

- 由SPA转换到基于多开窗口的MPA，每个不同的功能，如逻辑综合、时序分析、自动布局布线等都可以新开一个窗口，不再采用单APP多Page的模式，[Tauri已经开始支持多窗口模式]([Next.Js | MultiWindow | Open Links Support · Discussion #1163 · tauri-apps/tauri · GitHub](https://github.com/tauri-apps/tauri/discussions/1163))。

- db除了读取文件、提取数据和进行格式转换之外，还要在读取这些文件的基础上将他们存储到项目统一的数据库中（计划使用sqlite），每个项目一个数据库，存储原始数据和更改后的数据，第一次读取完数据后后续所有的操作都通过rust API来访问数据库数据进行数据建模而不是频繁地提取数据，当图形需要渲染时，直接从数据库中调取数据 - 待定，待议。

- 在图形方面，是基于数据模型的而不是简单地展示，用户可以通过输入命令，更改数据库中的数据模型或者缓存的数据模型，然后Web GUI只使用WebGL进行渲染。

### 软件开发稳定后的后续

- 开发自主算法，基于Rust，并直接采用pyo3进行绑定，或者编译成.wasm运行，看哪个省事。

## 学习资源（IC相关）

- IC EDA领域各种文件格式的作用：[here](http://www.vlsi-expert.com/p/different-file-formats-file-extensions.html)。着重注意以下几个通用的文件类型：
  - .lib, .db for Synopsys.
  - .lef, .def for Cadence.
  - .tf.
  - .map.
  - .slib, .sdb for Synopsys.
  - .mw, outdated. Not planned to support this currently.
  - .spef, .sbpf for Synopsys.
  - .v (verilog source file).
  - .v (gate-level netlist).

可能也是需要创建database来处理和存储这些通用的文件格式，优先支持这些通用的文件格式，关于这些文件的细节存在于*ref*文件夹下。

## ## IC 基础知识

- [vlsi universe](https://vlsiuniverse.blogspot.com/2014/07/propagation-delay.html)

- [比较难得的视频资源 - 整个IC物理设计EDA总览](https://www.bilibili.com/video/BV1XE411N7Er/?spm_id_from=333.788.recommend_more_video.0)

- [# 数字集成电路静态时序分析基础](https://www.bilibili.com/video/BV1if4y1p7Dq?spm_id_from=333.999.0.0)

## 赛事信息

- [蓝桥杯（立创）](https://www.lanqiao.cn/)
- [集成电路EDA设计精英挑战赛（行芯）](https://eda.icisc.cn/)
- [全国集成电路EDA开发应用技术技能大赛](http://iceda.org.cn/)

## 资源网站

### 总体设计

搜索EDA + script + language能找到不错的资源，感觉有用的包括

- [edaboard-类似国内eetop的网站，可能EDA本身的东西不多](https://www.edaboard.com/)

- [edasolutions-西门子家的网站，主页是推广，但这篇关于EDA脚本语言选择的文章不错，值得借鉴](https://www.eda-solutions.com/tn020/)

- [LinkedIn - python准备好在EDA领域](https://www.linkedin.com/pulse/python-all-set-disrupt-hw-verification-avidan-efody)

- [使用python库cocotb联合Cadence等仿真软件进行验证](https://indico.cern.ch/event/776422/attachments/1769690/2874927/cocotb_talk.pdf)

## 具体实现

#### Rust功能模块

- [LibrEDA - Codeberg.org](https://codeberg.org/LibrEDA)： 基于Rust的后端EDA算法功能集合，太棒了！！！

##### ~~Python - C、C++接口~~

- [2.8. Interfacing with C &#8212; Scipy lecture notes](http://scipy-lectures.org/advanced/interfacing_with_c/interfacing_with_c.html)

- [Getting Started &#8212; Cython 3.0.0a9 documentation](https://cython.readthedocs.io/en/latest/src/quickstart/index.html)

## 文献研究

文献都在*reference*文件夹下
