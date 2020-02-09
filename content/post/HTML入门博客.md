---
title: "HTML入门博客"
date: 2020-02-09T11:06:28+08:00
draft: false
---

# HTML入门博客

## 推荐书籍

  [HTML教程](https://wangdoc.com/html/index.html)

## 推荐在线代码编辑器

  ### JSBin

  地址：http://js.jirengu.com/ 

  特点：仅支持单文件编辑
  ### Codesandbox

  地址：https://codesandbox.io/

  特点：支持创建多文件，VSCode在线编辑器

## VScode代码格式化

  ### 安装插件-prettier
  1. 打开VScode，按下图操作搜索插件并安装；
     ![安装prettier](/static/images/install_prettier.png)

  2. 安装后重启VScode；
  3. 输入快捷键ctrl+shift+p，打开顶部的命令窗口，搜索：format document，可查看格式化的快捷键。
     ![安装prettier](/static/images/install_prettier2.png)

  ### 设置auto save
  1. 打卡VScode，点击【文件-首选项-设置】；
  2. 在“搜索设置”输入框输入【auto save】并搜索；
  3. 在搜索结果中将Auto save下拉选项设置为：onFocusChange
     ![设置auto save](/static/images/set_auto_save.png)

  ### 设置format on save
  1. 打卡VScode，点击【文件-首选项-设置】；
  2. 在“搜索设置”输入框输入【format on save】并搜索；
  3. 在搜索结果中将format on save下的勾选框设置为勾选状态。
     ![设置format on save](/static/images/set_format_on_save.png)
   
## HTML起手式
  1. 打开VSCode,新建文件：index.html
  2. 在index.html文件中输入快捷键【！+ tab】
  3. 自动补全起手式代码如下：
   ![HTML起手式](/static/images/html_start.png)

  ### 代码解析
  ```html
  <!DOCTYPE html>   <!---文档类型：html--->
  <html lang="en">  
  <!--1.html标签：页面的根标签，必须写；
      2.lang="en"：语言为英文；
      en-英文、zh-CN-中文 （通常用中文） 
  -->
  <head>   <!---head里面一般写页面看不到的元素--->
      <meta charset="UTF-8" />    <!---文件的字符编码为UTF-8--->
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />   <!---设置视窗，防止页面缩放--->
      <meta http-equiv="X-UA-Compatible" content="ie=edge" />   <!---如果当前页面在IE浏览器中显示，那么IE默认使用最新的内核--->
      <title>Document</title>   <!---网页的标题--->
  </head>
  <body></body>  <!---页面的内容--->
  </html>
   ```

## HTML标签
  
  ### 章节标签
  
  作用：表示文章、内容的层级
  * 标题h1-h6
  * 章节section
  * 文章article
  * 段落p
  * 头部header
  * 脚部footer
  * 主要内容main
  * 旁支内容aside
  * 划分div
  
  #### 代码示例
  ```html
  <!DOCTYPE html>
  <html>

  <head>
    <meta charset="utf-8">
    <title>JS Bin</title>
  </head>

  <body>
    <header>顶部广告</header>
    <div>
      <main>
        <h1>文章标题</h1>
        <h2>文章副标题</h2>
        <section>
          <h3>第一章</h3>
          <p>这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...这是第一章节的段落...第  </p>
        </section>
        <section>
          <h4>第1节</h4>
          <p>这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...这是第一节的段落...</p>
          <h5>第1.1节</h5>
          <h6>第1.1.1节</h6>
        </section>
      </main>
      <aside>参考书籍：xxxxx</aside>
    </div>
    <footer>&copy; 版权说明</footer>
  </body>
  </html>
  ```
  页面展示效果如下图所示：
  ![章节标签示例图](/static/images/section_label_.png)

  ### 全局属性
  作用：所有标签都有的属性
  * class
  * contenteditable
  * hidden
  * id
  * style
  * tabindex
  * title
  #### class
  ![全局属性-class](/static/images/global_attribute_class.png)

  #### contenteditable
  作用：可以使任何一个元素可以被编辑
  ![全局属性-contenteditable](/static/images/global_attribute_contenteditable.png)

  #### 如何让style的内容在页面显示
  + 将styel标签写在body部分
  + 增加style{display:block}样式即可
  + 若给style标签增加contenteditable属性，可在页面直接编辑样式
    ![display_style](/static/images/display_style.png)

  #### hidden
  作用：可以使任何一个元素被隐藏
  ![全局属性-hidden](/static/images/global_attribute_hidden.png)
  

  #### id
  注意：id必须唯一，但页面使用多个同名id不会报错，所以尽量使用class。
  #### style
  #### tabindex
  作用：设置键盘输入【tab】键时，选中哪个区域，控制tab的选中顺序
  注：tabindex特殊的值：0表示最后一个；-1表示不要访问
  下图分别设置了tabindex=1 2 3 表示第1 2 3 次按下【tab】键时选中的区域
  ![全局属性-tabindex](/static/images/global_attribute_tabindex.png)
  
  下图为第一次按下【tab】键选中的区域（蓝色框为选中区域）。
   ![tab_selectde_area](/static/images/tab_selectde_area.png)

  #### title
  作用：鼠标悬浮元素时的提示信息。可用来展示页面用...省略后的完整内容
    ![全局属性-tabindex](/static/images/global_attribute_tabindex.png)

  注：下面三行代码实现文字超长时用...省略
  ```css
    .head {
      border:1px solid red;
      white-space: nowrap;   /*作用：不要换行*/
      overflow: hidden;      /*作用：溢出内容省略*/
      text-overflow: ellipsis;     /*作用：省略部分用...代替*/   
        }
  ```
  ![全局属性-title](/static/images/global_attribute_title.png)
  

### CSS reset 默认样式
 #### 默认样式
  默认样式是html标签自带的样式，但已经不符合我们现在的需求，所以需要将默认样式重置。
  ![CSS_reset](/static/images/CSS_reset.png)

 #### css reset
  ![CSS_reset](/static/images/CSS_reset1.png)

 #### 淘宝网
 ```css
<style>
    blockquote,body,button,dd,dl,dt,fieldset,form,h1,h2,h3,h4,h5,h6,hr,input,legend,li,ol,p,pre,td,textarea,th,ul{margin:0;padding:0}body,button,input,select,textarea{font:12px/1.5 tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif}h1,h2,h3,h4,h5,h6{font-size:100%}address,cite,dfn,em,var{font-style:normal}code,kbd,pre,samp{font-family:courier new,courier,monospace}small{font-size:12px}ol,ul{list-style:none}a{text-decoration:none}a:hover{text-decoration:underline}sup{vertical-align:text-top}sub{vertical-align:text-bottom}legend{color:#000}fieldset,img{border:0}button,input,select,textarea{font-size:100%}button{border-radius:0}table{border-collapse:collapse;border-spacing:0}
</style>
 ```

### 内容标签
  - ol + li（ordered list + list item）
  - ul + li（unordered list + list item）
  - dl + dt + dd（description list + term + data）
  - pre（preview的缩写）
  - hr
  - br（break的缩写）
  - a（anchor的缩写）
  - em（emphasis的缩写）
  - strong
  - code
  - q（quote的缩写）
  - blockquotes
  #### ol + li（有序列表）
  全称：ordered list + list item 
  注：ol标签内只能有li标签，不能有其他的内容，包括文字、标签等。
  ```html
    <ol>
        <li>list item 1</li>
        <li>list item 2</li>
        <li>list item 3</li>
    </ol>
  ```
  效果图如下：
  ![Content_label_ol_li](/static/images/Content_label_ol_li.png)
  

  #### ul + li（无序列表）
  全称：unordered list + list item
  ```html
        <ul>
          <li>沟通需求</li>
          <li>领取任务</li>
          <li>写代码</li>
        </ul>
  ```
  ![Content_label_ul_li](/static/images/Content_label_ul_li.png)

  #### dl + dt + dd（描述对象的列表）
  全称：description list + term + data
  作用：dl为列表，dt内为描述的对象，dd为描述内容
  ![Content_label_dl_dt_dd](/static/images/Content_label_dl_dt_dd.png)

  #### pre（标签内空格原样输出）
  全称：preview的缩写
  html中，连续多个空格会自动识别为一个空格，多个回车也会识别为一个空格。
  pre标签可使得标签内的空格和回车原样输出。
  ![Content_label_pre](/static/images/Content_label_pre.png)
  
  #### hr（分割线）
  ![Content_label_hr](/static/images/Content_label_hr.png)
  
  #### br（换行）
  全称：break的缩写
  ![Content_label_br](/static/images/Content_label_br.png)

  #### a（链接）
  全称：anchor的缩写
  target="_black" ： 打开新窗口
  ![Content_label_a](/static/images/Content_label_a.png)
  
  #### em（主观强调）
  全称：emphasis的缩写
  表示主观强调重要
  #### strong（本身重要）
  表示内容本身重要
  #### code（代码标签）
  一般配合pre标签使用。
  ![Content_label_code](/static/images/Content_label_code.png)

  #### q（引用）
  全称：quote的缩写
  内联显示引用内容
  #### blockquote（块级引用）
  换行显示引用内容
 ![Content_label_q_blockquote](/static/images/Content_label_q_blockquote.png)
