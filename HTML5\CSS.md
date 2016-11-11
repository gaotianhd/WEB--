###1、Doctype？严格模式与混杂模式如何区分？它门有何意义？
     （1）、声明位于文档中的最前面，处于标签之前。告知浏览器的解析器，用什么文档类型规范来接系这个文档。
     （2）、严格模式的排版和JS运作模式是以该浏览器支持的最高标准运行。
     （3）、在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。
     （4）、DOCTYPE 不存在或格式不正确会导致文档以混杂模式呈现。
###2、HTML5为什么只需要写〈!Doctype html〉？
      HTML5不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）。
      而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。
###3、行内元素有哪些？块级元素有哪些？空元素有哪些？
     （1）CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认display值,比如div
         默认display属性值为"block",成为"块级"元素;  span默认display属性值为"inline"，是"行内"元素。
     （2）行内元素有：a b span img input select strong  块级元素有：div ul ol li dl dt dd h1 h2 
                   h3 h4 ...p    空元素有：br  hr  input  img
###4、页面导入样式时，使用link和@import有什么区别？
     （1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;
     （2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
     （3）import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题。
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
###11、请描述一下 cookies，sessionStorage 和 localStorage 的区别？
        cookie在浏览器和服务器间来回传递。sessionStorage和localStorage不会。
        sessionStorage和localStorage的存储空间更大;
        sessionStorage和localStorage有更多丰富易用的接口;
        sessionStorage和localStorage有各自独立的存储空间。
###12、iframe有那些缺点？
        iframe会阻塞页面的Onload事件;
        iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。使用iframe之前需要考虑这两个缺点。
        如果需要使用iframe，最好是通过javascript动态给iframe添加src属性值，这样可以绕开以上两个问题。
###13、Label的作用是什么？是怎么用的？（加for或包裹）
        作用：
            label往往出现在表单中，在表单中用label标签是为了提高用户体验，它最大最好的用途就在于：如果你只是想在界面呈现出来
            一些信息，而又不想让外界去操作，你给它赋什么值它就显示什么值，如果你不想让它显示信息的时候，就不给它赋值，操作起来
            很方便。
        用法：<label> 标签的 for 属性应当与相关元素的 id 属性相同。
             
             
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
###17、
      
       
       
