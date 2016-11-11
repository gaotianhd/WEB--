###1、Doctype？严格模式与混杂模式如何区分？它门有何意义？
答：告诉浏览器我们使用的是哪个版本的html协议（规范）。（对大小写不敏感）
严格模式中根据规范呈现页面；混杂模式中页面是一种比较宽松的向后兼容的方式显示。
（1）严格模式的HTML 4.0.1 strict
       答：告诉浏览器我们使用的是哪个版本的html协议（规范）。（对大小写不敏感）
       严格模式中根据规范呈现页面；混杂模式中页面是一种比较宽松的向后兼容的方式显示。
       （1）严格模式的HTML 4.0.1 strict
       DTD包括所有的HTML元素和属性，不包括展示的和弃用的元素。不许框架集（Framesets）
       <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
       （2）混杂模式
       DTD包括所有的HTML元素和属性，包括展示的和弃用的元素，以及框架集（Framesets）
       <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"
       "http://www.w3.org/TR/html4/frameset.dtd">
       模式之间差异：最显著的一个例子与Windows上IE专有的盒模型有关
       意义：DOCTYPE不存在或形式不正确会导致HTML和XHTML文档以混杂模式呈现。
###2、HTML5为什么只需要写〈!Doctype html〉？
      HTML5不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）。
      而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。
###3、行内元素有哪些？块级元素有哪些？空元素有哪些？
     答：行内元素：a-描点；em-强调；strong-粗体强调；span-定义文本内区块；i-斜体；img-图片；b-
         粗体；label-表格标签；select-项目选择；textarea-多行文本输入框；sub-下标；sup-上标；q-短引用
         块元素：div-常用块；dl-定义列表；dt；dd；ul-非排序列表；li-排序列表；ol-排序表单；p-段落；
         h1,h2,h3,h4,h5-标题；table-表格；form-表单
         空元素：br-换行；hr-水平分隔线
###4、页面导入样式时，使用link和@import有什么区别？
     答：相同的地方，都是外部引用CSS方式，区别：
        （1）link是xhtml标签，除了加载css外，还可以定义RSS等其他事务；@import属于CSS范畴，只能加载 CSS
        （2）link引用CSS时候，页面载入时同时加载；@import需要在页面完全加载以后加载
        （3）link是xhtml标签，无兼容问题；@import是在css2.1提出来的，低版本的浏览器不支持
        （4）link支持使用javascript控制去改变样式，而@import不支持
         最优化的@import url（style.css）最值得推荐，字节最优化，兼容的浏览器多。
###5、介绍一下你对浏览器内核的理解？
      主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和js引擎。
      渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显
      示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其
      它需要编辑、显示网络内容的应用程序 都需要内核。
      JS引擎则：解析和执行javascript来实现网页的动态效果。
      最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
###6、常见的浏览器内核有哪些？
       IE浏览器的内核Triednt、Mozilla的Gecko、Chrome的Blink(WebKit的分支)、Opera内核原为Presto，现为Blink；
       一、Trident内核代表产品Internet Explorer，又称其为IE内核。Trident（又称为MSHTML），是微软开发的一种排版引擎。
          使用Trident渲染引擎的浏览器包括：IE、傲游、世界之窗浏览器、Avant、腾讯TT、Netscape 8、NetCaptor、Sleipnir、
          GOSURF、GreenBrowser和KKman等。
       二、Gecko内核代表作品Mozilla FirefoxGecko是一套开放源代码的、以C++编写的网页排版引擎。Gecko是最流行的排版引擎之
          一，仅次于Trident。使用它的最著名浏览器有Firefox、Netscape6至9。
       三、WebKit内核代表作品Safari、Chromewebkit 是一个开源项目，包含了来自KDE项目和苹果公司的一些组件，主要用于Mac OS
          系统，它的特点在于源码结构清晰、渲染速度极快。缺点是对网页代码的兼容性不高，导致一些编写不标准的网页无法正常显示。主
          要代表作品有Safari和Google的浏览器Chrome。
       四、Presto内核代表作品OperaPresto是由Opera Software开发的浏览器排版引擎，供Opera7.0及以上使用。它取代了旧版Opera
          4至6版本使用的Elektra排版引擎，包括加入动态功能，例如网页或其部分可随着DOM及Script语法的事件而重新排版。
###7、HTML5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5？
      新特性：
      HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
      (1)绘画 canvas;
      (2)用于媒介回放的 video 和 audio 元素;
      (3)本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
      (4)sessionStorage 的数据在浏览器关闭后自动删除;
      (5)语意化更好的内容元素，比如 article、footer、header、nav、section;
      (6)表单控件，calendar、date、time、email、url、search;
      (7)新的技术webworker, websocket, Geolocation;
      
      移除的元素：
          纯表现的元素：basefont，big，center，font, s，strike，tt，u；
          对可用性产生负面影响的元素：frame，frameset，noframes。
      处理兼容问题有两种方式：
          1.IE8/IE7/IE6支持通过document.方法产生的标签，利用这一特性让这些浏览器支持HTML5新标签。
          2.使用是html5shim框架
      区分：
          DOCTYPE声明的方式是区分HTML和HTML5标志的一个重要因素，此外，还可以根据新增的结构、功能元素来加以区分。
###8、简述一下你对HTML语义化的理解？
        用正确的标签做正确的事情！
        HTML语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；在没有CSS样式的情况下也一种文档格式显示，并且
        是容易阅读的。搜索引擎的爬虫依赖于标记来确定上下文和哥哥关键字的权重，利于SEO。使阅读源代码的人更容易将网站
        分块，便于阅读理解。
###9、HTML5的离线储存怎么使用，工作原理能不能解释一下？
      原理：
         HTML5的离线存储是基于一个新建的.appcache文件的，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie
         一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。
                使用方法：
          1.在index.html里加上<html manifest="test.manifest">
           2.manifest清单格式如下：
          CACHE MANIFEST
          #上面一句必须
          #v1.0.0
          #需要缓存的文件
          CACHE:
          a.js
          b.css
          #不需要缓存的文件
          NETWORK:
          *
          #无法访问页面
          FALLBACK:
          404.html
          3.manifest文件的mime-type必须是 text/cache-manifest类型。
###10、浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？
        答：（1）html5是使用一个manifest文件来标明那些文件是需要被存储，对于manifest文件，文件的
             mime-type必须是text/cache-manifest类型。
            （2）cache manifest下直接写需要缓存的文件，这里指明文件被缓存到浏览器本地；在network下指明
             的文件，强制必须通过网络资源获取的；在failback下指明是一种失败的回调方案，比如无法访问，就
             发出404.htm请求。
###11、请描述一下 cookies，sessionStorage 和 localStorage 的区别？
        cookie在浏览器和服务器间来回传递。sessionStorage和localStorage不会。
        sessionStorage和localStorage的存储空间更大;
        sessionStorage和localStorage有更多丰富易用的接口;
        sessionStorage和localStorage有各自独立的存储空间。
###12、iframe有那些缺点？
        优点：1.iframe能够原封不动的把嵌入的网页展现出来。
        2.如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
        3.网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
        4.如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。

        缺点：（1）搜索引擎的“爬虫”程序无法解读这种页面。对于网站来说就是一种灾难
        （2）框架结构让人感到迷茫，几个框架中出现各种滚动条。
        （3）链接导航问题。使用框架结构时，保证设置正确的导航链接。
        （4）iframe页面会增加服务器的http请求（基本上都用ajax来代替iframe）
###13、Label的作用是什么？是怎么用的？（加for或包裹）
        Label 中有两个属性是非常有用的,一个是FOR、另外一个就是ACCESSKEY了。
        FOR属性
        功能：表示Label标签要绑定的HTML元素，你点击这个标签的时候，所绑定的元素将获取焦点。
        用法：<Label FOR="InputBox">姓名</Label><input ID="InputBox" type="text">
        ACCESSKEY属性：
        功能：表示访问Label标签所绑定的元素的热键，当您按下热键，所绑定的元素将获取焦点。
        用法：<Label FOR="InputBox" ACCESSKEY＝"N">姓名</Label><input ID="InputBox"
        type="text"> 
             
             
###14、HTML5的form如何关闭自动完成功能？
        有三种方法：
           1、在IE的Internet选项菜单里的内容--自动完成里面设置
           2、设置Form的autocomplete为"on"或者"off"来开启或者关闭自动完成功能
           3、设置输入框的autocomplete为"on"或者"off"来开启或者关闭该输入框的自动完成功能
###15、如何实现浏览器内多个标签页之间的通信?
         WebSocket、SharedWorker；
         也可以调用localstorge、cookies等本地存储方式；
         localstorge另一个浏览上下文里被添加、修改或删除时，它都会触发一个事件，
         我们通过监听事件，控制它的值来进行页面信息通信；
###16、webSocket如何兼容低浏览器？
         WebSocket是目前"唯一"的一个浏览器下的Socket的标准, 它是通过浏览器内部提供的API来实现访问的. 低版本的浏览器没有
         WebSocket这个标准, 就意味这些浏览器不允许用户通过它们来实现Socket通讯. 唯一的解决兼容性的办法就是准备一套Ajax 
         + Server-side Script的后备方案. 比如Ajax + PHP Socket.
         代码可以简单的写成
          var socket = new WebSocket('...') || function() {
          	// Ajax code
          }
###17、页面可见性(Page Visibility API)可以有哪些用途？
         JAVA API文档提供了很多官方的介绍和类、方法、变量的解释。一般很系统，涉及所有的方面，如果开发人员对正在使用的类不熟悉，
         想查看类里面的变量或者方法，就可以打开JavaAPI文档进行阅读和查看。 很多开发语言都提供了官方的文档，可以让开发人员迅速
         地提高能力。
###18、如何在页面上实现一个圆形的可点击区域？
        border-raduis
        使用border-raduis方法：假定设置一个宽高均为100px;然后给它设置一个border-raduis属性，给它设置一个点击事件就可以了，
        我们在这也可以设置一个cursor：pointer。
###19、实现不使用border画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都保持同一效果。
      
       
       
