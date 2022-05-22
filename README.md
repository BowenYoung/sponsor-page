# Sponsor-Page 捐赠小部件


参考项目：
<br />[Kaiyuan/sponsor-page](https://github.com/Kaiyuan/sponsor-page)
<br />[kelecn/sponsor-page](https://github.com/kelecn/sponsor-page)

## 效果：
<br />simple:
<br />![simple](https://raw.githubusercontent.com/BowenYoung/sponser-page/main/simple%20%20.gif)
<br />drinks:
<br />![drinks](https://raw.githubusercontent.com/BowenYoung/sponser-page/main/drinks%20%20.gif)


## 修改方法
先右上角fork本仓库（顺手可以一个star）。之后的修改在自己fork好的仓库中修改
### 修改文件
1. 将自己的支付宝收款码重命名为`AliPayQR.png`
  <br />微信收款码两份，一份重命名为`WeChanQR.png`，另一份重命名为`WeChanSQ.png`
  <br />QQ收款码重命名为`QQpay.png`
  <br />进入`\simple\images`目录将上述名称的文件删除后，上传自己的4个文件
2. 打开`/simple/index.html`
  <br />将第14行的`https://paypal.me/bowenyoung24`改为你的paypal收款链接
3. 打开`/drinks/index.html`
  <br />将第23行的`https://www.paypal.me/bowenyoung24`改为你的paypal收款链接
4. 打开`/drinks/script.js `
  <br />将第15行的`https://paypal.me/bowenyoung24`改为你的paypal收款链接
  <br />将第21行的`https://qr.alipay.com/fkx12803cjkw4cmcvt0jm77`改为你的支付宝收款链接（获取方法：PC端微信识别你的收款码，复制链接）
### 检查
将该仓库克隆到本地或直接下载。分别点击`simpe`下的`index.html`和`drinks`目录下的`index.html`查看效果。

## 在hexo博客中中插入捐赠部件
+ 在博客根目录的`source`文件夹中新建一个名为`donate`的文件夹将刚才的`simple`文件夹和`drinks`文件夹粘贴进去
+ 在`_config.yml`中添加
  ```
  skip_render: "donate/**" #hexo会跳过对该目录下文件的渲染（也就是保持你刚才看到的样子）
  ```
  
+ 部署完成后两个部件的访问链接就分别为:
  ```
  https://你的域名/donate/drinks
  https://你的域名/donate/simple
  ```
+ 插入到你的文章中
 1. 单独某篇文章使用
  在文章末尾添加html代码
  ```
  //simple对应引用代码
   {% raw %}
   </div>
   <iframe src="/donate/simple/" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
   </div>
   {% endraw %}
  ```
  ```
  //drinks对应引用代码
  {% raw %}
   </div>
   <iframe src="/donate/drinks/" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
   </div>
  {% endraw %}
  ```
 2. 每一篇文章都添加部件
  <br />需要修改文章布局文件（一般为`article.ejs`或者`article.jsx`之类的名字）
  <br />以Volantis主题为例，修改`themes\volantis\layout\_partial\article.ejs`
```
...
  </blockquote>
</div>

+ <div class='donate'>
+ <iframe src="/donate/drinks" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
+ </div>
```
通过</blockquote>可以快速定位，`+ `后面的是需要添加的内容
