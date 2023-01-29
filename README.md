# 统计LDD中导出的.xlsx格式的BOM零件表
本质上为对特定格式的.xlsx表格进行操作，因此暂时仅仅适用于LDD所导出的.xlsx格式的BOM表。
为什么用LDD导出的BOM表？
答：LDD导出的.xlsx表格中有零件的图片，便于手动采购散件。

---
## 功能与操作
1、通过与总零件表对比，统计需要对比的零件表中缺少的零件，并导出需要添加零件的表格：
**操作：** 点击“**选择已拥有的零件表**”选择自己的零件总表，点击“**选择新导出的零件表**”选择需要对比的零件表，选择了两表后，点击“**统计并导出需要添加的零件**”按钮，会在需要对比的零件表同目录下导出对比后的表格。“**统计数量恰好的零件**”选项默认勾选，便于添加备用零件。

2、基于添加零件的表格，向总表中添加或减少零件：
**操作：** 点击“**选择已拥有的零件表**”选择自己的零件总表，点击“**选择新添加的零件表**”选择需要添加的零件表，选择了两表后，点击“**合并添加的零件并导出表格**”按钮，会在零件总表同目录下导出添加后的表格。“**删除数量为0的零件**”选项默认勾选，会删除汇总后总表中数量为0的零件。

**注：** 若进度条卡住则代表发生错误，可以检查一下.xlsx表格格式。
___
## .xlsx表格格式
**1、总零件表与需要对比的零件表为LDD直接导出的格式，不需要对格式做任何修改：**
|Brick|Name|Picture|Part|Color code|Quantity|
|:----:|:----:|:----:|:----:|:----:|:----:|
|……|……|……|……|……|……|
|Total:|||||……|
**注：** 在LDD软件中LDD模式下导出的BOM表“Bick”列会有内容，而MINDSTORMS和Extended模式下brick一栏无内容，本程序对零件的判断“Brick”列中的内容要优先于“Part”与“Color code”。
**2、统计缺少的零件并导出的表格：**
|Brick|Name|Picture|Part|Color code|Quantity|add_QTY|
|:----:|:----:|:----:|:----:|:----:|:----:|:----:|
|……|……|……|……|……|……|……|
|Total:|||||……|……|
该表格为程序经过对比后导出的表格，新增了“add_QTY”一列，该列为需要需要增加的零件数量，**在向总表中添加或减少零件时读取的为“add_QTY”的零件数量**。
**注：** add_QTY一栏数据为负数则为减少零件，可以根据自己的需求灵活变更数量。