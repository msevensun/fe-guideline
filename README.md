##规范目的
  为提高团队协作效率， 便于后台人员添加功能及前端后期优化维护，输出高质量的代码， 特制订此文档，本规范文档一经确认， 前端开发人员必须按本文档规范进行前台页面开发， 本文档如有不对或者不合适的地方请及时提出

##基本准则
  符合web标准，语义化html， 结构 表现 行为分离，兼容性优良。 页面性能方面，代码要求简洁明了有序，尽可能的减小服务器负载， 保证最快的解析速度

##文件规范
1. Html/css/ js/ images文件均放在已约定的目录中
2. html文件命名： 英文命名，后缀.html(有扩展用 - 下划线链接扩展名)
3. css文件命名： 英文命名， 后缀.css，共用global.css/reset.css， 首页home.css， 其他页面依实际模块需求命名(有扩展用 - 破折号链接扩展名）
4. Js文件命名： 英文命名，后缀.js. 共用common.js, 其他依实际模块需求命名(有扩展用 - 破折号链接扩展名）

##图片规范
1. 所有页面元素类图片均放入images/imgs文件夹， 测试用图片放于test文件夹；需要sprite的图片放在temp文件夹以供备用，文件夹按模块划分
2. 图片格式仅限于gif /png/ jpg
3. 命名全部用小写英文字母、数字和 - 下划线的组合，其中不得包含汉字 、 空格、特殊字符；尽量用易懂相符的词汇，便于团队其他成员理解
4. 在保证视觉效果的情况下选择最小的图片格式与图片质量，以减少加载时间
6. 运用css sprite技术集中小的背景图或图标，减小页面http请求

##HTML规范
1. 代码统一使用小写
2. 使用html5的规范<!DOCTYPE html>
3. 使用utf-8编码
4. 把CSS文件放在<head>中，避免使用@import
5. 删除行尾空格
6. 书写链接地址时, 必须避免重定向，例如：href=”http://emao.com/”, 即须在URL地址后面加上“/”； 
7. 发布之前一定要进行压缩
8. 尽量使用有效的HTML代码
    - 编写有效的HTML代码，否则很难达到性能上的提升。
    - 用类似这样的工具 W3C HTML validator 来进行测试。

9. 根据HTML各个元素的用途而去使用它们。(语义化)
   使用元素 (有时候错称其为“标签”) 要知道为什么去使用它们和是否正确。 例如，用heading元素构造标题， p元素构造段落, a元素构造锚点等。根据HTML各个元素的用途而去使用是很重要的，它涉及到文档的可访问性、重用和代码效率等问题。
   <!-- 不推荐 -->
   `<div onclick="goToRecommendations();">All recommendations</div>`
   <!-- 推荐 -->
   `<a href="recommendations/">All recommendations</a>`
10. 在页面中尽量避免使用style属性,即style=”…”; （结构、表现、行为分离）
11. 在样式表和脚本的标签中忽略type属性
12. 不要使用实体引用 ，如—, ”但是 < 或是 &除外
13. 为多媒体元素（图像、视频音频、cavas创建的动态对象）提供替代内容，对图像来说可以在alt中加上有意义的文本内容，对视频音频来说可以加上描述性的元素
14. html文件以模块命名开头再细化（命名空间）
15. Css文件放在head中，js文件放在页面底部（js文件最好写在单独文件中，需要时引入页面）
16. 合理运用注释，避免使用中文注释（包括CSS）
17. 引入JS库文件, 在文件中须包含库名称及版本号及是否为压缩版, 比如jquery-1.11.1.min.js; 文件名改为软链接，比如把jquery-1.11.1.mis.js改为jquery.js或者jquery.mis.js；引入插件, 文件名格式为库名称+插件名称, 比如jQuery.cookie.js;

##CSS规范
1. 编码统一为utf-8;
2. 避免使用CSS表达式
3. 省略零值后面的单位和省掉起始的0值,margin: 0; padding: 0;font-size: .8px
4. 避免tag+id或者class+id，
  如：`button#goButton{...}；#goButton .fundation#testIcon {...}；`
  避免同时使用标签、ID和class作为定位一个元素选择器；从性能上考虑也应尽量减少选择器的层级。
5. 属性、十六进制尽量缩写(比如：color: #ffffff;缩写为：color: #fff;)
6. 省略URL中的引号（”或’）
7. ID或class名字前加上这种标识性前缀（命名空间），使用短破折号链接。比如：ad-help
8. 避免使用CSS “hacks”
9. 所有声明都要用“;”结尾
10. 在属性名冒号结束后加一个空字符，比如：font-weight: bold
11. 同一个类（class）中的样式属性统一单行书写
12. 对一个代码区块或模块进行注释
13. 规避class与id重名
14. 书写代码前, 考虑并提高样式重复使用率;
15. 背景图片请尽可能使用sprite技术, 减小http请求, 考虑到多人协作开发, sprite按模块划分制作;
16. 使用table标签时(尽量避免使用table标签)，请用css控制样式
17. css属性书写顺序, 建议遵循 布局定位属性–>自身属性–>文本属性–>其他属性. 此条可根据自身习惯书写, 但尽量保证同类属性写在一起. 属性列举:
    布局定位属性主要包括: margin/padding/float（包括clear）/position（相应的 top,right,bottom,left）/display/visibility/overflow等； 
    自身属性主要包括: width / height /background/border; 文本属性主要包括：　font/color/text-align/text-decoration/text-indent等；
    其他属性包括: list-style(列表样式)　/　vertical-vlign/cursor/z-index(层叠顺序) /zoom等. 
    此处所列出的这些属性只是最常用到的, 并不代表全部;

##js规范
1. 全站采用jQuery作为JS库，版本和版本号：1.11.1 / mini ,请不要修改此文件的任何内容。 位置：http://s.emao.net/js/jquery.js
2. js放置目录结构：公用类（common）、插件类（plugins）、模块类（所对应板块命名）比如新闻板块：js/news/news.js
3. common.js为全站通用脚本
4. Js代码必须基于jQuery进行构建
5. Js代码必须和html结构分离
>消息处理、跟踪/统计代码 、JS必须内置的特殊情况除外
6. 分离于页面之外的js文件必须采用utf-8无BOM格式编码，否则容易出现不可预知的乱码问题
7. 事件监听采用jQuery的高效监听机制。除极其特殊的要求外，禁止在脚本中出现onclick , onfoucs等事件
8. 良好的注释习惯
9. 格式请严格按照限定的格式书写。
    a.禁止向<script />标签添加language属性，省略type属性。

    b.外部调用的JS，确保先加载jquery.js 再加载基于jQuery开发的脚本，否则报错
10. 代码中统一使用单引号''。

##兼容性
  经产品确认，浏览器兼容方案如下：
1. 需完全兼容火狐、safari浏览器、chrome浏览器、ie浏览器（8、9、10）及以上三大内核的扩展浏览器如360急速、360安全、遨游、qq、搜狗等
2. ie6、ie7需无样式问题，可没有交互效果 

维护修改已有页面的时候，必须修正旧有页面存在的不符合规范的问题

