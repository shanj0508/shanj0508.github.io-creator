# HTML 常用标签

## 预览网页小工具

### http server

```javascript
//安装命令:安装后自动加入path，可以直接使用
$ yarn global add http-server
//使用命令 .可以省略；-c表示缓存，-c-1表示不需要缓存
$ http-server . -c-1
//缩写
$ hs -c-1
//执行命令后，给出访问链接，按住ctrl点击链接打开浏览器
//在url输入栏后面加上要打开的html页面的名称(例如：a-href.html)进行访问。
```

### parcel

```javascript
//安装命令
$ yarn global add parcel
//使用命令
$parcel xxx.html
//执行命令后，给出访问链接，按住ctrl点击链接打开浏览器
```

## a 标签

### 属性

#### href

全称：hyper reference 超级引用，超链接

```html
<a href="http://baidu.com" target="_blank" download>超链接</a>
```

##### 取值

- 网址
  - https://baidu.com
  - http://baidu.com
  - //baidu.com （//会自动选择是用 http 或 https）
- 路径 - /a/b/c 或 a/b/c - index.html 或 ./index.html
  ```html
  <a href="index.html">index.html</a>
  ```
- 伪协议

  - javascript:代码;

    : 和 ; 之间是可执行代码，点击超链接则执行代码；

    最常见的应用：是代码块部分为空，用来写一个点击后什么都不做的 a 标签。

    ```html
    <a href="javascript:alert(1);">javascript 伪协议</a>
    <a href="javascript:;">空的 javascript 伪协议</a>
    ```

  - mailto:邮箱

  ```html
  <a href="mailto:60xxxxxxx@qq.com">发邮件</a>
  ```

  - tel:手机号

  ```html
  <a href="tel:182xxxxxxxx">打电话</a>
  ```

- id(#xxx)--锚点定位

```html
//点击 a 链接，页面定位到 id="xxx"所在的标签
<p id="xxx">5</p>
<a href="#xxx">锚点定位</a>
```

#### target

作用：指定在哪个窗口打开超链接。（当前窗口或新开窗口）

```html
<a href="http://baidu.com" target="_blank">超链接</a>
```

##### 取值

- \_blank ：新开窗口跳转
- \_self：当前窗口跳转（默认值）
- \_top：顶层窗口（在页面中的 iframe 子页面中写 a 标签，指向 top 时，在浏览器顶层页面进行跳转）
- \_parent：父级窗口（在页面中的多层级的 iframe 子页面中写 a 标签，指向 parent 时，在当前 iframe 页面的父级页面中进行跳转）
- xxx：xxx 为自定义的 window 的 name

  作用：如果有一个叫做 xxx 的窗口，就在该窗口进行跳转，如果没有 xxx 窗口，则新开窗口进行跳 转，同时给新开的这个窗口命名为 xxx。

  优点：实现重复利用同一个窗口打开不同的页面。

  ```html
  //在页面点击【百度】超链接时，新开一个窗口进行跳转，并将窗口命名为 xxx
  //可在控制台输入：window.name 验证窗口名称
  //此时在页面点击【谷歌】超链接时，也在该新开的窗口 xxx 进行跳转
  <a href="//baidu.com" target="xxx">百度</a>
  <a href="//google.com" target="xxx">谷歌</a>
  ```

- xxx：xxx 为 iframe 的 name

  作用：在 ifram 页面中打开链接页面。

#### download

作用：下载页面，但很多浏览器不支持，了解即可。

#### rel=noopener

### 作用

- 跳转外部页面
- 跳转内部锚点
- 跳转到发邮件或打电话等

## iframe 标签

现在已经很少使用。

## table 标签

### 基本格式

```html
<table>
  <thead>
    ----头部，放置标题,可省略
    <tr>
      ----行
      <th></th>
      ---标题单元格
      <td></td>
      ---数据单元格
    </tr>
  </thead>
  <tbody></tbody>
  ---身体部分，放置数据内容，必填
  <tfoot></tfoot>
  ---脚部，可省略
</table>
```

### 示例

```html
<table>
  <thead>
    <tr>
      <th>英语</th>
      <th>翻译</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>hyper</td>
      <td>超级</td>
    </tr>
    <tr>
      <td>targer</td>
      <td>目标</td>
    </tr>
    <tr>
      <td>blank</td>
      <td>空白</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>111</td>
      <td>111</td>
    </tr>
  </tfoot>
</table>
```

### 相关样式

#### table-layout

```html
<style>
  table {
    width: 600px;
    table-layout: auto;
  }
</style>
```

##### 取值

- auto

  根据单元格的内容自动计算表格行和列的宽高，内容不同，宽高不同。

- fixed

  根据单元格的内容自动计算表格行和列的宽高，尽量保持各行各列平均分配宽高。

#### border-collapse

控制 border 是否合并

#### border-spacing

table 的 tr 和 td 之间默认有间距，border-spacing 可以控制 border 之间的距离，通常我们设置为 0。

```html
<style>
  table {
    width: 600px;
    table-layout: auto;
    border-spacing: 0;
    border-collapse: collapse;
  }
  th,
  td {
    border: 1px solid red;
  }
</style>
```

## img 标签

### 作用

发出 get 请求，展示一张图片

```html
<img src="dog.jpg" alt="一只dog" width="400" />
```

### 属性

#### src

源路径，填写图片的存放位置及路径

#### alt

若图片加载失败，则展示 alt 设置的内容

#### height

设置图片的高度，若只设置高度，则宽度自适应。

#### width

设置图片的宽度，若只设置宽度，则高度自适应。

注：若图片宽高都设置，但设置的并非图片本来的宽高，会导致图片变形，一定不能让图片变形。所以建议宽高设置一个即可。

### 事件

#### onload

图片加载成功触发的事件

#### onerror

图片加载失败触发的事件

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <img id="dog" src="dog1.jpg" alt="一只dog" width="400" />
    <script>
      dog.onload = function() {
        console.log("图片加载成功");
      };
      dog.onerror = function() {
        console.log("图片加载失败");
        dog.src = "dog2.png"; //当图片加载失败时，页面展示替换图片
      };
    </script>
  </body>
</html>
```

### 响应式

max-width: 100%;

设置最大宽度为当前屏幕宽度的百分之百，则页面拖拽或者不同手机都可以自适应宽度。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      img {
        max-width: 100%;
      }
    </style>
  </head>
  <body>
    <img id="dog" src="dog.jpg" alt="一只dog" />
    <script>
      dog.onload = function() {
        console.log("图片加载成功");
      };
      dog.onerror = function() {
        console.log("图片加载失败");
        dog.src = "dog2.png";
      };
    </script>
  </body>
</html>
```

### 可替换元素

https://developer.mozilla.org/zh-CN/docs/Web/CSS/Replaced_element

## form 标签

### 作用

发出 get 或 post 请求，然后刷新页面

```html
<form action="/xxx" method="POST" autocomplete="on" target="a"></form>
```

注：一个 form 表单，必须包含一个 type=“submit”的 input 或者 button 按钮

### 属性

#### action

控制请求哪个页面

#### method

控制请求方式是 get 还是 post

#### autocomplete

设置自动填充

- on-自动填充
- off-不自动填充

#### target

设置请求的页面在哪个页面打卡

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <form action="/xxx" method="POST" autocomplete="on" target="a">
      <input name="username" type="text" />
      <input type="submit" />
    </form>
    <iframe name="a" src="img.html" frameborder="0"></iframe>
  </body>
</html>
```

### 事件

#### onsubmit

作用：当用户点击提交时触发的事件。

## input 标签

### 作用

让用户输入内容

### 属性

- type
- name
- autofocus
- checked
- disabled
- maxlength
- pattern
- value
- placeholder

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    text:
    <!-- 普通文本输入框 -->
    <input type="text" required /><br />
    color:
    <!-- 输入框可选择颜色 -->
    <input type="color" /><br />
    password:
    <!--密码框输入框，输入的内容加密，显示为小圆点·····  -->
    <input type="password" /><br />
    radio:
    <!-- 单选框:将多个选项的name值设置为同一个，可实现单选功能 -->
    <input name="gender" type="radio" />男
    <input name="gender" type="radio" />女
    <br />
    checkbox:
    <!-- 复选框：建议将多个选项的name值设置为相同，表示是同一组 -->
    <input name="hobby" type="checkbox" />爱好1
    <input name="hobby" type="checkbox" />爱好2
    <input name="hobby" type="checkbox" />爱好3
    <br />
    file:
    <!-- 选择单个文件 -->
    <input type="file" />
    <!-- 选择多个文件 -->
    <input type="file" multiple />
    <br />
    hidden:
    <!-- 隐藏输入框:用来给js自动填入一些信息和内容，例如ID、字符串等 -->
    <input type="hidden" />
    <br />
    textarea:
    <!-- 文本域：多行输入框 -->
    <textarea></textarea> <br />
    <!-- 设置文本域不可拖拽大小 -->
    <textarea style="resize: none;width: 50%; height: 300px;"></textarea>
    <br />
    select：
    <!-- 下拉选择框：value为真正的值，文本为页面显示的值，默认值value为空 -->
    <select>
      <option value="">-请选择-</option>
      <option value="1">选项1</option>
      <option value="2">选项2</option>
      <option value="3">选项3</option>
    </select>
    <br />
    submit:
    <!-- 提交按钮 -->
    <input type="submit" />
    button：
    <!-- 提交按钮 -->
    <button type="submit">提交</button>
    <!-- 上面两者的区别：button中间可以有任何内容，包括文本、标签等，input只能通过value设置文本，不能设置标签等其他内容 -->
  </body>
</html>
```

### 事件

#### onchange

当用户输入改变时，触发事件

#### onfocus

当用户将鼠标集中在某个标签上时，触发事件

#### onblur

当用户将鼠标移出时，触发事件

### 验证器

HTML5 新增功能
例如：

```html
<input type="text" required /><br />
//require 就是一个自带的验证功能，若上面的文本框为空，则提交时提示不能为空。
```

### 注意事项

- 一般不监听 input 的 click 事件
- form 里面的 input 要有 name
- form 里面要放一个 type=submit 才能触发 submit 事件

## 其他输入标签

### select+option

```html
select：

<!-- 下拉选择框：value为真正的值，文本为页面显示的值，默认值value为空 -->
<select>
  <option value="">-请选择-</option>
  <option value="1">选项 1</option>
  <option value="2">选项 2</option>
  <option value="3">选项 3</option>
</select>
```

### textarea

```html
textarea textarea:

<!-- 文本域：多行输入框 -->

<textarea></textarea> <br />

<!-- 设置文本域不可拖拽大小 -->

<textarea style="resize: none;width: 50%; height: 300px;"></textarea>
<br />
```

### label

## 其他标签

### video

### audio

### canvas

### svg

### 注意事项

这些标签的兼容性要查看文档
