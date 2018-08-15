# fontspider
## 痛点：设计图里经常出现代表整个页面风格的特殊字体。
#### 传统解决方案
1. 使用切图（切图工作量大，且UI图终版之后 产品或业务更改文案 需修改psd文件并再次切图）。
2. 使用UI提供的 .ttf 字体文件（文件过大，一般都在 2M以上，多则7~10M,影响页面样式加载）。

#### 目前解决方案
* 使用UI提供的原始 .ttf 字体文件生成自己所需的 .ttf 文件。
* 生成的 .ttf 文件能缩小至 5kb~150kb（所需字体数多少 文件大小有差别，字数越多文件越大）。

#### 缺点
* 需在项目上线之前知道所需文案所需文字的全集。

#### 原理
* 使用 font-spider 插件工具从原始的 .ttf 文件中抽出你所需的字 重新生成一个 .ttf 和 .woff 字体文件。
* 参考文档链接为：[http://font-spider.org/](http://font-spider.org/)。

#### 使用步骤
1. 将 font/ 目录下的 myfont.ttf 替换为你自己所需的特殊字体文件，注意：必须是 .ttf 文件。
2. 将 html/index.html 文件中 ``` <p></p> ``` 标签中填入你所需转换的文字全集。  
  2.1 例如你需要文案中包含数字 0~9 你就把 0123456789 填入 ``` <p></p> ```标签中。  
  2.2 如还有其他文案就继续往```<p></p>```标签中添加相应的文字就行了。  
  2.3 最终生成 .ttf 和 .woff文件时 能自动识别重复的文字。不用自己做文字去重工作。
3. 安装依赖 ``` npm install ```
4. 运行 ``` npm run dev ``` 或者 ``` gulp dev ```
5. 查看页面 [http://localhost:8888/html/index.html](http://localhost:8888/html/index.html) 页面上的效果就是字体样式。
6. 运行 ``` npm run build ``` 或者 ``` gulp build ```
7. 将 build/目录下的 .ttf .woff 文件拷贝至自己的项目就可以使用字体文件了。
