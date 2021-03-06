## JavaScript 历史 ##
 JavaScript的诞生的主要是当时的 `netspace` 公司谋求为自己的浏览器 `Navigator` 添加一种脚本语言，以便在本地客户端进行一些行为操作，而这一功能的需求源于当时网络带宽很低（当时还是采用拨号上网，ADSL，网速基本也就28.8Kbit/s），对于一些表单的验证操作，用户只能提交到服务器，然后由服务端进行验证，再将结果通过网络反馈给用户。这种方式的效率无疑是很低的，所以当时 `Navigator` 的运营者们就想，能否在浏览器中嵌入一种编程语言，来直接实现这一验证行为，当时他们也考虑了是否将 JAVA内置到浏览器中，但是JAVA这门语言对于浏览器而言过于庞大。最终还是决定重新开发一门专为浏览器打造的语言，并聘请了当时具有很深厚的函数式编程开发背景的“布兰登·艾奇 Brendan Eich” 来着手开发。
 
当时的任务很紧急，因为这门语言预计要于1992年2月发布的 Navigator 2.0 一同发布用于增强产品在市场上的关注度。所以 布兰登·艾奇在借鉴了C、JAVA、prel等当时流行的语言后，只用了不到10天就开发出了这门新的语言，当时将其命名为 `LiveScript`，后来 Netspace 公司又与 SUN 公司达成联盟，为了搭上媒体热炒JAVA的顺风车，临时又将 `LiveScript` 改名为 `JavaScript` 。

搭有 `JavaScript 1.0` 的 `Navigator 2.0` 在市场上的推广非常成功，`netspace` 当时也在浏览器技术革新的道路上走到了最前沿，之后 `netspace`公司满怀信心的进行 `JavaScript 1.1` 的开发，并将其内置在了1996年发布的 `Navigator 3.0` 中，`JavaScript` 这门语言为浏览器带来的优势并没有被当时刚开始做浏览器的 `Microsoft` 所忽视，因此微软也在其 IE3.0中内置了一个 `JScript1.0`，这个 `JScript1.0` 可以是说一个完全山寨于 `JavaScript 1.1` 的，它们具有相同的功能，但是底层的实现上完全不同，虽然 IE凭借 `JScript1.0` 也占有技术优势，但是不同的版本并存的 `JavaScript`以及微软并不完整的功能模仿也为以后的兼容性埋下了坑。

或许是为了解决未来的兼容性问题，也或许是为了保持对市场和技术的领先地位，在1997年，`netspace` 以 `JavaScript 1.0`  为蓝本的建议被提交给了欧洲计算机制造商协会(ECMA) 来进行“标准化”。在同一年，在提交标准化申请后 ,netsapce再次满怀信心的进行了 `JavaScript 1.2` 的开发，并将其内置在了 `Navigator 4.0` 中。而到这一年底，ECMA-262 第一版才被接受并实现了标准化，结果，虽然，ECMAScript 被认为是基于 `JavaScript1.1` 为蓝本来制定的，但是最新的 `JavaScript1.2` 与 ECMAScript第一版并不兼容。

`JScript`的升级版是 IE4.0中内置的 `JScript3.0`(随同ISS3.0发布的JScript2.0从来没有移植到浏览器中)，微软虽然也在大肆宣传 JScript3.0是世界上第一个与ECMA兼容的脚本语言，但当时的 ECMAScript-262 还尚未定稿，于是 JScript3.0 与 JavaScript1.2都遭遇了相同的尴尬局面 --- 那就是谁都没有按照最终的 ECMAScript标准来实现。

一直到了 `Netspace Navigator 4.06` ，其中发布的 `JavaScript 1.3` 才做到了与 ECMAScript第一版完全兼容，在 `JavaScript 1.3` 除了兼容 ECMAScript，还增加了对Unicode标准的支持，并同时保留了 `JavaScript 1.2` 中未按标准实现的新特性，同时也实现了所有对象平台的中立化。而IE则是到了 IE5才完全兼容 ECMAScript第一版。

## ECMAScript ##
1997年当ECMA接受了 `netspace` 以 `JavaScript 1.0` 为蓝本的标准化建议后，该协会指定第39号技术委员会（TC39,Technical Commottee #39）来负责“标准化一种通用，跨平台、供应商中立地的脚本语言的语法和语义”。TC39的主要组成成员是 netspace，Sun，微软，Borland以及其它关注脚本语言的发展公司和程序员组成，他们经过数月的努力完成了 ECMA-262 - 定义了一种名为 ECMAScript的新脚本语言标准。随后的第二年，ISO/IEC(International Organization for Standardization，国际标准化组织) 也采用了 ECMAScript标准，即 ISO/IEC-16262。

ECMA-262 定义的 ECMAScript 是一门独立于平台（与宿主环境无关）的脚本语言，这门语言本身并有包含输入和输出的定义。因此不同的宿主环境可根据自己的需要在这个基础上构建更完善的适合自己环境的脚本语言 ，例如我们常见的Web浏览器、Adobe Flash以及服务端的Node，都是ECMAScript的宿主环境之一，不同的宿主环境都会 在ECMAScript的基础上加以自己的扩展，以便语言与环境之间可以更好的交互和对接。

ECMAScript本质上就是对实现该标准规定的各个方面内容的语言的描述，大致来说，它规定了这门语言的下列组成部分：
    
* 语法
* 类型
* 语句
* 关键字/保留字
* 操作符
* 对象：（对象要做到与平台无关）

对于语言功能的具体实现，则是交由不同的厂商自己去实现，实现的方法与过程可以不同，但是最终的结果要与标准定义的一致。

在兼容性上，ECMA-262 给的定义是，要想成为 ECMAScript的实现，则该实现必须做到以下几点：

* 支持ECMA-262中对ECMAScript的所有描述以及定义。
* 支持Unicode字符集
* 在ECMAScript中可以结合自己的需求进行扩展，例如更多的类型、值、对象、属性和函数（ECMA-262所定义的这些新增特性，主要是指标准中没有规定的新对象和新属性）
* 支持ECMA-262没有定义的”程序和正则表达式语法“（也就是说可以扩展内置的正则表达式语法）

从1997年年底发布的第一个ECMAScript版本依赖，它主要经过了以下的版本迭代：

**ECMAScript 第一版（ECMAScript 1.0）**
基本上与 `JavaScript1.1` 相同，只是删除了所有有关浏览器的代码，支持 了 `Unicode` 字符集，而且语言中的对象也变成了与平台无关。

**ECMAScript 第二版（ECMAScript 2.0）**
这一版本主要是编辑加工的结果，其内容的更新是为了与 ISO/IEC-16262保持严格的一致，没有做任何新增，修改或者删除处理，因此不使用 `ECMAScript2.0` 来衡量 ECMAScript的兼容性。

**ECMAScript 第三版（ECMAScript 3.0）**
该版对 ECMAScript 开始了真正的修改，修改的内容涉及到了字符处理、错误定义、数值输出、这一版还新增了对正则表达式、新控制语句、try-cacth异常捕获的支持。并围绕着标准的国际化做出了一些小的修改，从各方面来看，`ECMAScript3.0` 标志着 ECMAScript成为了一门真正的编程语言。

**ECMAScript 第四版（ECMAScript 4.0）**
在这一版的修订上，TC39委员会的成员们根据是否对之前的版本进行微小的修改，以兼容 `ECMAScript 3.0` 还是完全舍弃之前的标准，从新定义一门新的语言而产生了分歧，最终守旧派战胜了求新派，`ECMAScript4.0` 并没有得到通过，而是对之前版本进行小幅修订并能够在现有 JavaScript引擎基础上实现的 `ECMAScript3.1` 得到了通过。

**ECMAScript 第五版（ECMAScript 5.0）**
当 `ECMAScript4.0` 在正式发布之前便被废弃后`ECMAScript3.1` 成了 ECMA-262的第五个版本，并于2009年12月3日正式发布。
第5版力求澄清第3版中已知的歧义并增添了一些新的功能，例如原生 JSON的对象、继承的方法和高级属性定义、对数组方法的扩展、严格模式等等。

下面是当时各个主流浏览器厂商对 ECMAScript各个版本的支持情况

| 浏览器  |  ECMAScript兼容性 |
| :--    |  :---:    |       
| Navigator4.06 ~ 4.79      | ECMAScript 1.0   | 
| Navigator6(Mozilla 0.6.0)+     | ECMAScript 3.0   | 
| IE5.0     | ECMAScript 1.0   | 
| IE5.5 - IE7.0     | ECMAScript 3.0   | 
| IE8.0    | ECMAScript 5.0*   | 
| IE9.0    | ECMAScript 5.0   | 
| Opera6-7.1   | ECMAScript 1.0   | 
| Opera6-7.2+   | ECMAScript 3.0   | 
| Safari1.0 ~ 2.x   | ECMAScript 3.0*   | 
| Safari3.0+  | ECMAScript 3.0   | 
| Safari4.0 ~ 5.x  | ECMAScript 5.0*   | 
| Chrome 1+ | ECMAScript 3.0  | 
| Firefox 1 ~ 3.x | ECMAScript 3.0  | 
| Firefox 3.5 ~ 3.6 | ECMAScript 5.0*  | 
| Firefox 4.0 | ECMAScript 5.0  | 

注：* 不完全兼容的实现。 


## JavaScript组成 ##
`JavaScript` 是基于浏览器宿主环境的对`ECMAScript`标准的实现，除了提供基本语法的`ECMAScript`，实际上`JavaScript` 还包含了 `DOM`、`BOM` 等两大部分：

![Javascript.png-8.9kB][1]

* ECMAScript：规定了JavaScript的基础语法
* DOM：文档对象模型。
* BOM：浏览器对象模型。


## 文档对象模型（DOM） ##
DOM (Document Object Model，文档对象模型)，它是JavaScript访问并控制页面元素以及内容的API（Application Programming Interface）。
DOM 把整个页面映射为一个多层节点结构（树型图），然后结合 JavaScript 来获取，修改，删除，替换这些节点，从而实现不需要重新加载页便可以修改页面的内容以及外观。

在DOM提出之前，IE4 以及 NN4 分别支持不同形式的 DHTML(Dynamic HTML)技术，这种技术本质上是一种营销的噱头，它实际上是融合了（HTML,CSS,JS）三种技术的统称，而 DHTML技术在不同的浏览器厂商具体的实现标准也不相同，netspace和微软对 DHTML 技术实现也各持己见，使得 WEB开发领域出现技术上的两强割据，浏览器互不兼容的局面快速加深，此时，负责制定WEB通信标准的W3C，开始着手规划 DOM的标准化。

DOM 与 DHTML的区别主要在于 DOM的把 JavaScript对页面的操作单独的拿了出来，并进行了标准化，
DOM与 ECMAScript一样，也经过了很多的版本迭代：

**DOM 0级**
实际上并不存在 DOM 0 级，我们常常看到关于DOM0级的字眼，实际上是对DOM历史发展的一种参照而已，具体的来说，DOM 0级指的IE4.0以及NN4.0最初实现的DHTML技术。
**DOM 1级**
DOM Level 1 于1998年10月成为 W3C推荐标准。
其主要功能就是映射文档的结构，对页面的不同的节点进行访问和操作。

**DOM 2级**
DOM Level 2 是在 DOM LEVEL 1 的基础上加以扩展，相比较DOM1，DOM2支持的功能要更加的多，DOM2级在原来的 DOM基础上扩充了（DHTML一直都支持的）鼠标和用户界面事件、节点的范围遍历（迭代DOM节点）、并且通过对象接口增加了对了CSS的支持。
DOM2级主要引入了以下的新模块，也给出了众多的新类型和新接口的定义，可以说从DOM2级开始，DOM才能完全的达到并超过之前DHTML技术的功能。

* DOM视图(DOM views) ：定义了根据不同文档（例如，应用CSS之前和之后的文档）视图的接口。
* DOM事件（DOM Event：定义了事件和处理的接口
* DOM 样式（DOM STYLE）: 可以为元素（节点）应用样式的接口。
* DOM 遍历和范围 （DOM Traversal and Range）: 定义了遍历和操作文档树的接口。

**DOM3级**
DOM LEVEL 3进一步的对 DOM 进行了扩展，比如引入了统一式加载和保存文档树的接口，新增了验证文档的方法。

DOM 在组成上则有两个模块组成：DOM Core(DOM 核心)、DOM HTML。前者规定了一种统一映射文档结构的方法，而后者则是在DOM核心的基础上加以扩展，添加了专门针对 HTML文档的对象和方法，或许这样说，DOM Core 是一种通用的 DOM标准，它可以作用在XML,HTML等标记语言上，而 DOM HTML 则是专门为 HTML的操作进行的私有扩展。

下面是不同浏览器对 DOM级别的支持情况：

| 浏览器  |  DOM Level |
| :--    |  :---:    |       
| Navigator6(Mozilla 0.6.0)+     | 1、2(*)、3(?) |
| IE5.0      |  1(?) |
| IE5.5 ~ IE8.0      |   1、2(*)    | 
| IE9.0     |   1、2、3| 
| Opera 7 ~ 8.x     |   1(*)、2(?)| 
| Opera 9 ~ 9.9    |   1、2(*)、3（？）| 
| Opera 10.0 +     |   1、2、3（*）| 
| Safari 1.0.x    |   1| 
| Safari 2+    |   1、2(*) | 
| chrome 1+    |   1、2(*) | 
| firefox 1+    |   1、2(*)、3(?)| 

注 : * 表示大部分支持 ?表示小部分支持。



## 浏览器对象模型（BOM） ##
BOM：(Borwser Object Model，浏览器对象模型)，与DOM相同，BOM是 JavaScript访问并控制浏览器状态的API。更形象的说，就是开发人员可以通过 BOM来控制浏览器中显示页面以外的部分。
大致上来说，BOM可以实现以下功能：

* 弹出浏览器窗口的功能
* 移动、缩放、和关闭浏览器窗口的功能
* 提供浏览器详细信息的 navigator对象
* 提供浏览器所加载页面的的详细信息的location对象
* 提供用户显示器分辨率信息的scren对象。
* 对cookies的支持
* 一些像 XMLHttpRequest 和 ActiveXObject 浏览器自定义的对象。

需要注意的是 BOM 到目前为止还没有一个标准化组织去进行标准化定义，不过未来的HTML5 将会把BOM的标准纳入其中。



  [1]: ./assets/Javascript.png