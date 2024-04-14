---
layout: post
title:  Markdown basic gramer
date:   2024-04-14 22:16:46 +0000
author: "GentaLee"
categories: jekyll update
---
# 南風NOTOS github文章使用基础语法（基于markdown）
**创建.md文档,打开同步预览功能，开始编辑**
###二、 基本语法
1. **标题**
    #一级标题
    ##二级标题
...

2. **引用**
    > 编辑这类教程文档很好用!
    #> 即可打开引用，常用在代码上

3. **列表**
    1. 无序列表
    - 列表1
    + 列表2
    * 列表3
    2. 有序列表
    3. 嵌套
    4. TodoList
        - [x] a
        - [ ] b
        - [ ] c

4. **表格**
    | 左对齐 | 居中对齐 | 右对齐 |
    | :----- | :----: | ----: |
    | a | b | c |

5. **段落**
    - 换行？ —— 两个以上空格后回车/空一行
    - 分割线 —— 三个*
     ***
    - 字体
        | 字体 | 代码 |
        | :--: | :--: |
        |*斜体*|* *|
        |==高亮==|== ==|
        |**粗体**|** **|
        |***粗斜体***|*** ***|
        |~~删除~~|~~ ~~|
        |<u>下划线</u>|```<u> </u>```|
      - 脚注
        少年共创荣耀，青春比翼南風[^1]!
[^1]:南風队训

6.**代码**
    ```
   #include<iostream>
   using namespace std;
   int main(){
    print("hello world");
   }
    ```
    `printf("hello world");`

7.**超链接**
    [直接将链接放置在方括号内]:https://www.bilibili.com/video/BV1Su4y1y7k9/?spm_id_from=333.337.search-card.all.click&vd_source=59e8703ee442d8783ded7322b6c338ef

###三、 其他操作
   - **插入latex**
     - 行内显示公式：
    $f(x)=ax+b$
   - 块内显示数学表达式:
    $$
    \begin{Bmatrix}
    a & b \\
    c & d
    \end{Bmatrix}
    $$
   - **html/css语法**
    -ctrl+shift+p 搜索
    "Markdown Preview
    Enhanced:Customize CSS"
    在style中使用css语法改标题格式等
   - **个性化设置**
    File-Preferences-Settings
