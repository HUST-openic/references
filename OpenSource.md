# Open Source Collection for IC EDA design

All are open source softwares. Watch out the licenses.

- [Open Source collection of Yosys](https://www.yosyshq.com/open-source), including Yosys and more.

- [Verilog to Routing · GitHub](https://github.com/verilog-to-routing), including tatum (STA) and more.

- [[GitHub - The-OpenROAD-Project/OpenROAD: OpenROAD&#39;s unified application implementing an RTL-to-GDS Flow](https://github.com/The-OpenROAD-Project/OpenROAD). 比较全面的，RTL2GDS流程，包括了基础功能又不是很复杂，适合用rust重写c++来作为基础功能测试的模块。

- [LibrEDA - Codeberg.org](https://codeberg.org/LibrEDA), 一个全用rust写的EDA工具，而且同样适用的是python binding。可以参考上面的rust写法和用法，**优先**研究他的应用和设计，学习怎么写的，然后自己开发app，实在不行那就加入他。

What we need to do is to:

- Get binaries (ideally wasm) from open source code.

- Build connection between binaries/codes between python.
