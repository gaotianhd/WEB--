###1、Doctype？严格模式与混杂模式如何区分？它门有何意义？
       答：
           告诉浏览器我们使用的是哪个版本的html协议（规范）。（对大小写不敏感）
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
      答：
         表示声明Html5标准网页，支持html5标准主流浏览器都认识这个声明。
###3、行内元素有哪些？块级元素有哪些？空元素有哪些？
      答：
         行内元素：a-描点；em-强调；strong-粗体强调；span-定义文本内区块；i-斜体；img-图片；b-
         粗体；label-表格标签；select-项目选择；textarea-多行文本输入框；sub-下标；sup-上标；q-短引用
         块元素：div-常用块；dl-定义列表；dt；dd；ul-非排序列表；li-排序列表；ol-排序表单；p-段落；
         h1,h2,h3,h4,h5-标题；table-表格；form-表单
         空元素：br-换行；hr-水平分隔线
###4、页面导入样式时，使用link和@import有什么区别？
      答：
         相同的地方，都是外部引用CSS方式，区别：
        （1）link是xhtml标签，除了加载css外，还可以定义RSS等其他事务；@import属于CSS范畴，只能加载 CSS
        （2）link引用CSS时候，页面载入时同时加载；@import需要在页面完全加载以后加载
        （3）link是xhtml标签，无兼容问题；@import是在css2.1提出来的，低版本的浏览器不支持
        （4）link支持使用javascript控制去改变样式，而@import不支持
         最优化的@import url（style.css）最值得推荐，字节最优化，兼容的浏览器多。
###5、介绍一下你对浏览器内核的理解？
         答：
         主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和js引擎。
         渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网
         页的显示方式，然后会输出至显示器或打印 机。浏览器的内核的不同对于网页的语法解释会有不同，
         所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用
         程序 都需要内核。
         JS引擎则：解析和执行javascript来实现网页的动态效果。
         最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
###6、常见的浏览器内核有哪些？
        答:
           （1）Trident 微软的排版引擎 IE7修正许多CSS排版上的错误以及增加对PNG格式的支持：IE，The World
           （2）Geckos 开源的浏览器，:FireFox，seamonkey
           （3）presto 渲染速度极速：opera7以上版本
           （4）webkit 苹果公司的内核，包含webcore排版引擎和javascript解析引擎。：safari，chrome
###7、HTML5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5？
       答：
           新增加了图像、位置、存储、多任务等功能。
           新增几大类：
              (1)绘画 canvas;
              (2)用于媒介回放的 video 和 audio 元素;
              (3)本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
              (4)sessionStorage 的数据在浏览器关闭后自动删除;
              (5)语意化更好的内容元素，比如 article、footer、header、nav、section;
              (6)表单控件，calendar、date、time、email、url、search;
              (7)新的技术webworker, websocket, Geolocation;
           移除的元素：
              （1）显示层元素：basefont，big，center，font，s，strike，tt，u
              （2）性能较差元素：frame，frameset，noframes
           处理HTML5新标签的浏览器兼容问题：
              （1）IE8、7、6支持document方法产生的标签
              （2）使用htmlshim框架
           区分：
              （1）doctype声明的方式是区分重要因素
              （2）根据新增加的结构、功能来区分
###8、简述一下你对HTML语义化的理解？
        答：
           用正确的标签做正确的事情。根据内容结构化。选择合适的标签，便于开发者阅读和写出更优雅的代码，同时让
           浏览器的爬虫进行解析。
###9、HTML5的离线储存怎么使用，工作原理能不能解释一下？
         答：
            所谓的离线存储就是将一些资源文件保存在本地，这样后续的页面加载将使用本地的资源文件，在离线的情况下
            可以继续访问web应用。
         原理：
             HTML5 的离线存储是基于一个新建的.appcache 文件的缓存机制（不是存储技术），通过这个文件上的解析
             清单离 线存储资源，这些资源就会像cookie一样被存储了下来。
###10、浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？
        答：
            （1）html5是使用一个manifest文件来标明那些文件是需要被存储，对于manifest文件，文件的
             mime-type必须是text/cache-manifest类型。
            （2）cache manifest下直接写需要缓存的文件，这里指明文件被缓存到浏览器本地；在network下指明
             的文件，强制必须通过网络资源获取的；在failback下指明是一种失败的回调方案，比如无法访问，就
             发出404.htm请求。
###11、请描述一下 cookies，sessionStorage 和 localStorage 的区别？
          答：
          共同点：都是保存在浏览器端，且是同源的。
          区别：
          （1）cookies始终是http中携带，即cookie在浏览器和服务器间来回传递，而sessionstorage和localstorage
          不会自动把数据发给服务器，仅在本地保存。
          （2）存储大小的限制不同。cookie保存的数据很小，不能超过4k，而sessionstorage和localstorage保存的数
          据大，可达到5M。
          （3）数据的有效期不同。cookie只在设置的cookie过期时间之前一直有效，即使窗口或者浏览器关闭。sessionstorage
          仅在浏览器窗口关闭之前有效。localstorage始终有效，窗口和浏览器关闭也一直保存，用作长久数据保存。
          （4）作用域不同。cookie在所有的同源窗口都是共享；sessionstorage不在不同的浏览器共享，即使同一页面，locals
          torage在所有同源窗口都是共享的。
###12、iframe有那些缺点？
        答：
          优点：
               1.iframe能够原封不动的把嵌入的网页展现出来。
               2.如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
               3.网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
               4.如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。

          缺点：
              （1）搜索引擎的“爬虫”程序无法解读这种页面。对于网站来说就是一种灾难
              （2）框架结构让人感到迷茫，几个框架中出现各种滚动条。
              （3）链接导航问题。使用框架结构时，保证设置正确的导航链接。
              （4）iframe页面会增加服务器的http请求（基本上都用ajax来代替iframe）
###13、Label的作用是什么？是怎么用的？（加for或包裹）
       答：
          Label 中有两个属性是非常有用的,一个是FOR、另外一个就是ACCESSKEY了。
          FOR属性
          功能：表示Label标签要绑定的HTML元素，你点击这个标签的时候，所绑定的元素将获取焦点。
          用法：<Label FOR="InputBox">姓名</Label><input ID="InputBox" type="text">
          ACCESSKEY属性：
          功能：表示访问Label标签所绑定的元素的热键，当您按下热键，所绑定的元素将获取焦点。
          用法：<Label FOR="InputBox" ACCESSKEY＝"N">姓名</Label><input ID="InputBox"
              type="text"> 
             
             
###14、HTML5的form如何关闭自动完成功能？
       答：
          HTML的输入框可以拥有自动完成的功能，当你往输入框输入内容的时候，浏览器会从你以前的同名
          输入框的历史记录中查找出类似的内容并列在输入框下面，这样就不用全部输入进去了，直接选择列表
          中的项目就可以了。

          但有时候我们希望关闭输入框的自动完成功能，例如当用户输入内容的时候，我们希望使用AJAX技术从
          数据库搜索并列举而不是在用户的历史记录中搜索。

       方法：
            1、在IE的internet选项菜单中里的内容--自动完成里面设置
            2、设置form的autocomplete为on或者off来来开启输入框的自动完成功能。
            3、设置输入框的autocomplete为on或者off来开启或者关闭输入框自动完成的功能。
###15、如何实现浏览器内多个标签页之间的通信?
         答：
             WebSocket、SharedWorker;也可以调用 localstorge、cookies 等本地存储方式;localstorge 另一个浏览上下
             文里被添加、修改或删除时，它都会触发一个事件，我们通过监听事件，控制它的值来进行页面信息通信;注意 quirks：
             Safari 在无痕模式下设置 localstorge 值时会抛出QuotaExceededError 的异常;
###16、webSocket如何兼容低浏览器？
        答：
        只是引用了WebSocket.js这个文件来兼容低版本浏览器。
###17、页面可见性(Page Visibility API)可以有哪些用途？
        答：
           （1）通过visibilitystate的值得检测页面当前是否可见，以及打开网页的时间
           （2）在页面被切换到其他后台进程时，自动暂停音乐或视频的播放。
###18、如何在页面上实现一个圆形的可点击区域？
       答：    
           （1）map+area或者svg
           （2）border-radius
           （3）纯js实现，一个点不在圆上简单算法、获取鼠标坐标
###19、实现不使用border画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都保持同一效果。
       答：
       <div style="height:1px;overflow:hidden;background:red"></div>
###20、网页验证码是干嘛的，是为了解决什么安全问题？
       答：
            （1）区分用户是计算机还是人的公共全自动程序。
            （2）可以防止恶意破解密码、刷票、论坛灌水；可以有效防止黑客对某一个特定的注册用户用特定的程序暴力破
             解进行不断的尝试。
###21、title与h1的区别、b与strong的区别、i与em的区别？
        答：
            （1）title属性没有明确意义，只表示标题；h1表示层次明确的标题，对页面信息的抓取也有很大的影响
            （2）strong标明重点内容，语气加强含义；b是展示强调内容
            （3）i是内容是斜体；em表示强调文本
        注：
             自然样式标签：b，i，u，s
             语义样式标签：strong，em，ins，del，code  
###22、介绍一下标准的CSS盒子模型？低版本IE的盒子模型有什么不同？
        答：
             标准的CSS盒子模型：宽度=内容的宽度+边框的宽度+内边距宽度
             低版本的盒子模型：指的是内容的宽度
###23、CSS选择符有哪些？哪些属性可以继承/
        答：
            （1）类选择符；id选择符；
            （2）class属性，伪类a标签，列a表ul，li，dl，dd，dt
        注：
             优先级（就近原则）：!important > [ id > class > tag ]
             Important 比 内联优先级高
###24、CSS优先级算法如何计算？
        答：
              元素选择符：0,0,0,1
              一个class选择符：0,0,1,0
              一个id选择符：0,1,0,0
              一个元素标签：1,0,0,0,
        注： 
        注意：
             （1）!important声明的样式优先级最高，如果冲突再进行计算。
             （2）如果优先级相同，则选择最后出现的样式。
             （3）继承得到的样式的优先级最低。
###25、CSS3新增伪类有哪些？
        答：
               p:first-of-type 选择属于其父元素的首个元素的每个元素。
               p:last-of-type 选择属于其父元素的最后元素的每个元素。
               p:only-of-type 选择属于其父元素唯一的元素的每个元素。
               p:only-child 选择属于其父元素的唯一子元素的每个元素。
               p:nth-child(2) 选择属于其父元素的第二个子元素的每个元素。
               :enabled :disabled 控制表单控件的禁用状态。
               :checked 单选框或复选框被选中。
###26、如何居中div?如何居中一个浮动元素？如何让绝对定位的div居中？
        答：
           居中div：
               margin：0 auto
           浮动元素的居中：
              （1）父级div设置固定宽度，加上margin：0 auto，子级div浮动
              （2）在table中插入div，div设置浮动，在table上设置margin：0 auto，而table不要设置宽度。
           绝对定位的居中：
              （1）外层的相对定位的大div用margin：0 auto；然后这个绝对定位用left或者top来调。
###27、display有哪些值？说明他们的作用。
        答：
           常用的（显示）：
               inline（默认）--内嵌
               none--隐藏
               block--块显示
               table--表格显示
               list-item--项目列表    
###28、position的值relative和absolute定位原点是？
        答：
               static（默认）：按照正常文档流进行排列
               relative（相对定位）参照父级的原始点为原始点，无父级则以BODY的原始点为原始点
               absolute(绝对定位)原点：离自己这一级元素最近的一级postion的父元素的左上角，参照浏览器的左
               上角，配合left，right，top，bottom。
###29、CSS有哪些新特性？
        答：
               （1）选择器
               （2）RGBA和透明度
               （3）多栏布局 ：background-origin（图片定位区域）：content-box/padding-box/border-box
               （4）多背景图：background-image：url...，url...
               （5）word-wrap（对长的不可分割单词换行）word-wrap：break-world
               （6）文字阴影：text-shadow： 5px 5px 5px #FF0000;（水平阴影，垂直阴影，模糊距离，阴影颜色）
               （7）font-face属性：定义自己的字体，@font-face
                {
                font-family: myFirstFont;
                src: url('Sansation_Light.ttf'),
                url('Sansation_Light.eot'); /* IE9+ */
                }
                div
                {
                font-family:myFirstFont;
                }
               （8）圆角（边框半径）：border-radius 属性用于创建圆角
               （9）边框图片：border-image:url(border.png) 30 30 round;
               （10）盒阴影：box-shadow: 10px 10px 5px #888888;
               （11）盒子大小：background-size(图片尺寸大小)：63px 100px；background-repeat：no-repeat；
               （设置百分比是拉伸）；
               （12)媒体查询：定义两套css，当浏览器的尺寸变化时会采用不同的属性。
               （13）语音
###30、请解释一下CSS3的Flexbox（弹性盒布局模型），以及适用场景？
        答：
               称为弹性盒布局模型是css3规范中的一种新的布局方式，该布局模型的目的是提供一种更加高效的方式来对容器中
               的条目进行布局、对齐和分配空间。在传统的布局方式中，block 布局是把块在垂直方向从上到下依次排列的；而
               inline 布局则是在水平方向来排列。弹性盒布局并没有这样内在的方向限制，可以由开发人员自由操作。
###31、用纯CSS创建一个三角形的原理是什么？
        答：    
               首先，需要把元素的宽度、高度设为0。然后设置边框样式。
                    {
                    width: 0;
                    height: 0;
                    border-top: 40px solid transparent;
                    border-left: 40px solid #ff0000;
                    border-bottom: 40px solid transparent;
                    }
###32、一个满屏品字布局如何设计？
        答：      
               第一种（真正的品字）思路：
              （1）三块高宽是确定的；
              （2）上面那块用margin: 0 auto;居中；
              （3）下面两块用float或者inline-block不换行；
              （4）用margin调整位置使他们居中。

               第二种（全屏的品字布局）
               基本思路：上面的div设置成100%，下面的div分别宽50%，然后使用float或者inline使其不换行。
###33、经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hark的技巧?
        答： 
           问题：
               （1）问题一：不同浏览器的标签默认的margin和padding不同
               （2）问题二：块属性标签float后，又有横行的margin情况下，在IE6显示margin比设置的大
               （3）问题三：设置较小高度标签（一般小于10px），在IE6，IE7，遨游中高度超出自己设置高度
           原因：
                因为不同浏览器使用内核及所支持的HTML（标准通用标记语言下的一个应用）等网页语言标准不同；
                以及用户客户端的环境不同（如分辨率不同）造成的显示效果不能达到理想效果。
           hark解决的方法：
               （1）hack：*{margin:0;padding:0;}
               （2）hack：display:inline;将其转化为行内属性
               （3）hack：给超出高度的标签设置overflow:hidden;或者设置行高line-height 小于你设置的高度
###34、li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？
        答：
                因为代码之间的间距造成的
           解决方法：
               （1）浮动li中float：left
               （2）在ul中用font-size：0（谷歌不支持）；可以使用letter-space：-3px
###35、为什么要初始化CSS样式？
        答：
                每一个html标签都有自己的默认样式，而css就是可以改变html的样式。但是对于大量div设置就很麻烦，
                所以初始化样式很重要。
###36、absolute的containing block计算方式跟正常流有什么不同？
        答：     
                position属性：normalflow（一般流）；containing block（包含块）；bfc（）；margincollapse
                （float引起元素塌陷）；base line（基线对齐）
                一个元素盒子的位置和大小有时是通过相对于一个特定的长方形来计算的，这个长方形就被称之为元素的 
                containing block。


                <HTML>
                <HEAD>
                <TITLE>Illustration of containing blocks</TITLE>
                </HEAD>
                <BODY id="body">
                <DIV id="div1">
                <P id="p1">This is text in the first paragraph…</P>
                <P id="p2">This is text <EM id="em1"> in the
                <STRONG id="strong1">second</STRONG> paragraph.</EM></P>
                </DIV>
                </BODY>
                </HTML>

                产生盒子的元素 其包含块 C.B.（正常计算）
                body initial C.B. (UA-dependent)
                div1 body
                p1 div1
                p2 div1
                em1 p2
                strong1 p2

                如果我们按如下方式放置 em1：
                #div1 { position: absolute; left: 50px; top: 50px }
                #em1 { position: absolute; left: 100px; top: 100px }
                containing blocks 变成如下：

                产生盒子的元素 其 包含块C.B. 为
                body initial C.B.
                div1 initial C.B.
                p1 div1
                p2 div1
                em1 div1
                strong1 em1
###37、CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下有什么区别？
        答：     
                当一个元素的visibility属性被设置成collapse值后，对于一般的元素，它的表现跟hidden是一样的。
               （1）谷歌浏览器中，使用collapse值和使用hidden没有区别。
               （2）火狐，opera和IE，使用collapse值和使用display：none没有什么区别，下面的内容会补充他的内容。 
###38、position跟display、margin、overflow、float这些特性相互叠加后会怎样？
        答：     
                display属性规定元素应该生成的框的类型；
                position属性规定元素的定位类型；
                float属性是一种布局方式，定义元素在哪个方向浮动。
                类似于优先级机制：position：absolute/fixed优先级最高，有他们在时，float浮动不起作用，display
                值需要调整。浮动或者absolute定位的元素，只能是块元素或表格。
###39、对BFC规范(块级格式化上下文：block formatting context)的理解？
        答：    
           定位方案：
              （1）普通流（normal flow）
               按照html中的先后位置至上而下布局，行内元素水平排列，当前行被占满后换行，块级元素会被渲染为完整的新行。
              （2）浮动（floats）
               元素首先按照普通流位置出现，然后根据浮动的方向尽可能的向左向右偏移，与印刷的文本环绕相似。
              （3）绝对定位（absolute position）
               绝对定位中，元素会整体脱离普通流

               BFC正是属于普通流，因此对兄弟元素也不会造成什么影响。
               具有 BFC 的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且BFC具有普通
               容器没有的一些特性。
               浮动元素，绝对定位元素，display，overflow会触发BFC。
               
          特性：
              （1）会阻止外边距折叠
              （2）会包含浮动元素
              （3）阻止元素被浮动元素覆盖
###40、CSS权重优先级是如何计算的？
        答：
               标签的权重为1，class权重为10，id的权重为100.避免权重相同的发生。
###41、请解释一下为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式？
        答：
              （1）出现浮动之后，我们可以很好的进行页面布局
              （2）在非IE浏览器（如Firefox）下，当容器的高度为auto，且容器的内容中有浮动（float为left或
                  right）的元素，在这种情况下，容器的高度不能自动伸长以适应内容的高度，使得内容溢出到容器外
                  面而影响（甚至破坏）布局的现象。这个现象叫浮动溢出，为了防止这个现象的出现而进行的CSS处理
                  ，就叫CSS清除浮动
              （3）第一种方式是不对浮动的文本和图像进行清理，而是选择浮动容器div：
                  第二种方式：利用overflow属性。应用值为hidden或auto的overflow属性有一个有用的副作用，这会自
                  动清理包含的任何浮动元素
                  第三种方式：结合使用:after伪类和内容声明在指定的现有内容的末尾添加新的内容：

                  .clear:after {
                  　content:".";
                  　height:0;
                  　visibility:hidden;
                  　display:block;
                  　clear:both;
                  }

                  <div class="news clear">
                  　...
                  </div>
###42、移动端的布局用过媒体查询吗？
        答：
              通过媒体查询可以为不同大小和尺寸的媒体定义不同的css，适应相应的设备的显示
              @media screen and （min-width：400px）and （max-width：700px）{...}
###43、使用 CSS 预处理器吗？喜欢哪个？
        答：
           预处理器：
              less，sass等等（给css像其他程序语言一样，加入一些编程元素，让css能像其他程序
              语言一样做一些预定的处理，然后就有了css预处理器）喜欢Sass，less，stylus。Sass 是采用 Ruby
              语言编写的一款 CSS 预处理语言
              ：$color:red
              .test{
              color：$color;s
              }
              执行结果：
              .test{
              color：red;
              }

              (1)Sass 语法
              $font-stack: Helvetica, sans-serif //定义变量
              $primary-color: #333 //定义变量

              body
              font: 100% $font-stack
              color: $primary-color

              (2)SCSS 语法
              $font-stack: Helvetica, sans-serif;
              $primary-color: #333;

              body {
              font: 100% $font-stack;
              color: $primary-color;
              }
              编译出来的 CSS
              body {
              font: 100% Helvetica, sans-serif;
              color: #333;
              }
###44、CSS优化、提高性能的方法有哪些？
        答：
            （1）避免过度约束
             // 糟糕
             ul#nav{..}

             // 好的
             #nav{..}

            （2）后代选择符不好
             html div tr td {..}

            （3）避免链式选择符
             // 糟糕
             .menu.left.icon {..}

             // 好的
             .menu-left-icon {..}
            （4）使用复合（紧凑）语法
             // 糟糕
             .someclass {
             padding-top: 20px;
             padding-bottom: 20px;
             padding-left: 10px;
             padding-right: 10px;
             background: #000;
             background-image: url(../imgs/carrot.png);
             background-position: bottom;
             background-repeat: repeat-x;
             }

             // 好的
             .someclass {
             padding: 20px 10px 20px 10px;
             background: #000 url(../imgs/carrot.png) repeat-x bottom;
             }
            （5）避免不必要的命名空间
             // 糟糕
             .someclass table tr.otherclass td.somerule {..}

             //好的
             .someclass .otherclass td.somerule {..}
             （6）避免不必要的重复
             .someclass {
             color: red;
             background: blue;
             font-size: 15px;
             }

             .otherclass {
             color: red;
             background: blue;
             font-size: 15px;
             }

             // 好的

             .someclass, .otherclass {
             color: red;
             background: blue;
             font-size: 15px;
             }
            （7）最好使用表示语义的名字。一个好的类名应该是描述他是什么而不是像什么
            （8）避免！important，可以选择其他选择器
            （9）尽可能的精简规则，你可以合并不同类里的重复规则  
###45、浏览器是怎样解析CSS选择器的？
        答：
             而在 CSS 解析完毕后，需要将解析的结果与 DOM Tree 的内容一起进行分析建立一棵 RenderTree，最终用来进行
             绘图。在建立 Render Tree 时（WebKit 中的「Attachment」过程），浏览器就要为每个 DOM Tree 中的元素
             根据 CSS 的解析结果（Style Rules）来确定生成怎样的 renderer。
###46、在网页中的应该使用奇数还是偶数的字体？为什么呢？
        答：
             使用的是偶数字体。
             偶数字号相对更容易和 web 设计的其他部分构成比例关系。Windows 自带的点阵宋体（中易宋体）从 Vista 开始只
             提供 12、14、16 px 这三个大小的点阵，而 13、15、17 px时用的是小一号的点阵（即每个字占
             的空间大了 1 px，但点阵没变），于是略显稀疏。
###47、margin和padding分别适合什么场景使用？
        答：
          何时使用margin：
            （1）需要在border外侧添加空白
            （2）空白处不需要背景色
            （3）上下相连的两个盒子之间的空白，需要相互抵消时。
          何时使用padding：
            （1）需要在border内侧添加空白
            （2）空白处需要背景颜色
            （3）上下相连的两个盒子的空白，希望为两者之和。
          兼容性的问题：
             在IE5 IE6中，为float的盒子指定margin时，左侧的margin可能会变成两倍的宽度。通过改变padding或者指定盒子
             的display：inline解决。
###48、抽离样式模块怎么写，说出思路，有无实践经验？[阿里航旅的面试题]
        答：
             暂
             时
             没
             有
             答
             案
###49、元素竖向的百分比设定是相对于容器的高度吗？
        答：
           PS：
             当按百分比设定一个元素的宽度时，它是相对于父容器的宽度计算的。竖向距离的属性，如padding-top,padding-
             bottom,margin-top,margin-bottom等，当按百分比设定它们时，依据的也是父容器的宽度，而不是高度
###50、全屏滚动的原理是什么？用到了CSS的哪些属性？
        答：
            （1）原理：
             方法一是整体的元素一直排列下去，假设有5个需要展示的全屏页面，那么高度是500%，只是展示100%，剩下的可以通
             过transform进行y轴定位，也可以通过margin-top实现
            （2）overflow：hidden；
             transition：all 1000ms ease；
###51、什么是响应式设计?响应式设计的基本原理是什么？如何兼容低版本的IE？
        答：
            （1）响应式网站设计(Responsive Web design)的理念是：集中创建页面的图片排版大小，可以智能地根据用户行
             为以及使用的设备环境（系统平台、屏幕尺寸、屏幕定向等）进行相对应的布局。
            （2）基本原理: 媒体查询 @media
            （3）兼容IE可以使用JS辅助一下来解决
###52、视差滚动效果，如给每页做不同的动画？（回到顶部，向下滑动要在次出现，和只出现一次分别怎么做？）
        答：
             视差滚动（Parallax Scrolling）就是这样的效果之一。这种技术通过在网页向下滚动的时候，控制背景的移动速
             度比前景的移动速度慢来创建出令人惊叹的3D效果。
          原理：
            （1）CSS3实现
             优点：开发时间短、性能和开发效率比较好，缺点是不能兼容到低版本的浏览器
            （2）jquery实现
             通过控制不同层滚动速度，计算每一层的时间，控制滚动效果。
             优点：能兼容到各个版本的，效果可控性好
             缺点：开发起来对制作者要求高
            （3）插件实现方式
             例如：parallax-scrolling，兼容性十分好
###53、::before和:after中双冒号和单冒号有什么区别？解释一下这两个伪元素的作用。
        答：
            （1）单冒号(:)用于CSS3伪类，双冒号(::)用于CSS3伪元素
             在css2之前用的是单冒号，之后css3使用时双冒号。目前除了IE外不兼容双冒号，其他的浏览器兼容双冒号，建议
             还是使用单冒号。
            （2）：：before就是以一个子元素的存在，定义在元素主体内容之前的一个伪元素。并不存在与dom之中，只存在在
             页面之中。同理，after是在主体内容之后显示的。
###54、如何修改chrome记住密码后自动填充表单的黄色背景？
        答：
             这黄色背景是chrome会默认给自动填充的input表单加上input：-webkit-autofill私有属性
             input：-webkit-autofill{
             background-color : #FAFFBD ;
             background-image : none ;
             color : #000
             }
          第一种情况：input文本框是纯色背景的
             可以对input：-webkit-autofill使用足够大的纯色内阴影来覆盖input输入框的黄色背景
             input:-webkit-autofill{
             -webkit-box-shadow:0 0 0px 1000px white inset;
             border：1px solid #ccc ！important;
             }
             除了chrome默认定义的background-color，background-image，color不能用!important提升其优先级
             以外，其他的属性均可使用!important提升其优先级
          第二种情况：input文本框使用背景图片
             1、图片不复杂可以使用第一种情况解决，纯色内阴影覆盖
             2、使用js实现;存在一个问题是使用js方法会导致提交表单的时候无法将value值传过去。
             3、使用form标签上的关闭自动填充功能：autocomplete="off"
###55、你对line-height是如何理解的？
        答：
           行高是指一行文字的高度，具体说是两行文字间基线的距离。
             css中起高度作用的因该是height和line-height，一个没有定义height属性，最终其表现作用一定是
             line-height。
             单行文本垂直居中：把line-height值设置为height一样大小的值可以实现单行文字的垂直居中，其实
             也可以把height删除。
             多行文本垂直居中：需要设置display属性为inline-block。
###56、设置元素浮动后，该元素的display值是多少？（自动变成display:block）
        答：
             display：block
           IE出现双边框的原因：
             浮动元素的浮动方向与margin的方向一致会出现双边框。
           解决bug：
            （1）给浮动元素添加一个display：inline
            （2）给IE6写一个hack，其值为正常值的一半。
###57、怎么让Chrome支持小于12px 的文字？
        答：
           方法一：
             首先取消浏览器自动调整功能。
             .classstyle{ -webkit-text-size-adjust:none; font-size:9px; } （现在无效）
           方法二：
             现在可以使用css3里的一个属性：transform：scale（）
             p{font-size:10px;-webkit-transform:scale(0.8);}//0.8是缩放比例
###58、让页面里的字体变清晰，变细用CSS怎么做？（-webkit-font-smoothing: antialiased;）
        答：
             -webkit-font-smoothing在window系统下没有起作用，但是在IOS设备上起作用
             -webkit-font-smoothing：antialiased是最佳的，灰度平滑。
###59、font-style属性可以让它赋值为“oblique” oblique是什么意思？
        答：
             在css规范中这么描述的，让一种字体表示为斜体（oblique），如果没有这样样式，就可以使用italic。
             oblique是一种倾斜的文字，不是斜体。
###60、position:fixed;在android下无效怎么处理？
        答：
             在head头中加入
           <meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0,
           minimum-scale=1.0, user-scalable=no"/>
###61、如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）
        答：
             多数显示器默认频率是60Hz，即1秒刷新60次，所以理论上最小间隔为1/60＊1000ms ＝ 16.7ms
###62、display:inline-block 什么时候会显示间隙？(携程)
        答：
            （1）有空格时候会有间隙 解决：移除空格
            （2）margin正值的时候 解决：margin使用负值
            （3）使用font-size时候 解决：font-size:0、letter-spacing、word-spacing
###63、overflow: scroll时不能平滑滚动的问题怎么处理？
        答：
            （1）高度尺寸不确定的时候，使用：overflow-y：scroll;
            （2）高度尺寸确定的，要么没有滚动条，要么直接出现，不会出现跳动。
            （3）css3计算calc和vw单位巧妙实现滚动条出现页面不跳动：
                .wrap-outer {
                margin-left: calc(100vw - 100%);
                }
             或.wrap-outer {
              padding-left: calc(100vw - 100%);
              }
             首先，.wrap-outer指的是居中定宽主体的父级，如果没有，创建一个
             然后，calc是css3的计算
             100vw是浏览器的内部宽度，而100%是可用宽度，不含滚动条
             calc（100vw-100%）是浏览器的滚动条的宽度
###64、有一个高度自适应的div，里面有两个div，一个高度100px，希望另一个填满剩下的高度。
        答：
            （1）height：calc（100%-100px）
            （2）absolute positioning：外层position：relative；
             百分百自适应元素 position: absolute; top: 100px; bottom: 0; left: 0
###65、png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？
        答：
            （1）png是便携式网络图片（Portable Network Graphics）是一种无损数据压缩位图文件格式，
                 优点是：压缩比高，色彩好。 大多数地方都可以用。
            （2）jpg是一种针对相片使用的一种失真压缩方法，是一种破坏性的压缩，在色调及颜色平滑变化做的不错。在www上，
             被用来储存和传输照片的格式。
            （3）gif是一种位图文件格式，以8位色重现真色彩的图像。可以实现动画效果时候

             webp格式
             是谷歌在2010年推出的图片格式，压缩率只有jpg的2/3，大小比png小了45%，缺点是压缩的时间更久了。兼容性不
             好，目前谷歌和opera支持。
###66、什么是Cookie 隔离？（或者说：请求资源的时候不要让它带cookie怎么做）
        答：
             Cookie隔离问题，同一个网页,多个RemoteWebDriver会共享同一个Cookie。比如想要并行登陆并执行操作，这样
             是不行的。
###67、style标签写在body后与body前有什么区别？
        答：  
             页面加载自上而下，当然应该先加载样式，把style放在body前面。
###68、什么是CSS 预处理器 / 后处理器？
        答：
          CSS预处理器：
             CSS 预处理器是一种语言，用来为 CSS 增加一些编程的的特性，无需考虑浏览器的兼容性问题
             例如你可以在 CSS 中使用变量、简单的程序逻辑、函数等等在编程语言中的一些基本技巧，可以让你的CSS更见简洁，
             适应性更强，代码更直观等诸多好处
             Sass、LESS、Stylus 是目前最主流的 CSS 预处理器
          以 LESS 为例：
             LESS
             .opacity(@opacity: 100) {
             opacity: @opacity / 100;
             filter: ~"alpha(opacity=@{opacity})";
             }
             .sidebar {
             .opacity(50);
             }

          以上 DSL 源代码 (LESS)，编译成 CSS：
             .sidebar {
             opacity: 0.5;
             filter: alpha(opacity=50);
             }
          实现原理：
             1. 取到 DSL 源代码 的 分析树
             2. 将含有动态生成相关节点的分析树 转换为 静态分析树
             3. 将 静态分析树 转换为 CSS 的 静态分析树
             4. 将 CSS 的 静态分析树 转换为 CSS 代码
          优点：
             语言级逻辑处理，动态特性，改善项目结构
          缺点：
             采用特殊语法，框架耦合度高，复杂度高。
             
             
          CSS后处理器：
              CSS 后处理器 是对 CSS 进行处理，并最终生成 CSS 的 预处理器，它属于广义上的 CSS 预处理器比如最近比较
              火的 Autoprefixer，可以对css自动处理兼容性问题
          示例：
          以 Autoprefixer 为例：
              .container {
              display: flex;
              }
              .item {
              flex: 1;
              }
          将以上标准CSS，编译为处理了兼容性的 生产环境 CSS：

             .container {
             display: -webkit-box;
             display: -webkit-flex;
             display: -ms-flexbox;
             display: flex;
             }
             .item {
             -webkit-box-flex: 1;
             -webkit-flex: 1;
             -ms-flex: 1;
             flex: 1;
             }
          可以看到，编译前 与 编译后 的代码都是 CSS
   
          实现原理：
             1. 将 源代码 做为 CSS 解析，获得 分析树
             2. 对 CSS 的 分析树 进行 后处理
             3. 将 CSS 的 分析树 转换为 CSS 代码
          优点：
             使用 CSS 语法，容易进行模块化，贴近 CSS 的未来标准
          缺点：
             逻辑处理能力有限



          
