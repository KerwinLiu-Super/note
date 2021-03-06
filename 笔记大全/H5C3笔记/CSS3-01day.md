#### 01-认识css3

+ 什么是css3？

   CSS3是CSS2的“进化”版本，在CSS2基础上，增强或新增了许多特性，弥补了CSS2的众多不足之处，使得 Web开发变得更为高效和便捷

+ css3现状

  + 浏览器支持程度差，需要添加私有前缀 
  + 移动端支持优于PC端 
  + 不断改进中
  + 应用相对广泛

+ 如何对待css3兼容问题？

  + 渐进增强（Progressive Enhancement）：一开始就针对低版本浏览器进行构建页面，完成基本的功能，然后再针对高级浏览器进行效果、交互、追加功能达到更好的体验。
  + 优雅降级（Graceful Degradation）：一开始就构建站点的完整功能，然后针对浏览器测试和修复。比如一开始使用 CSS3 的特性构建了一个应用，然后逐步针对各大浏览器进行 hack 使其可以在低版本浏览器上正常浏览。
  + 考虑用户群体：例如医院、银行等政府网站基本不需要c3
  + 听产品经理的
  + 听boss的

#### 02-属性选择器

+  E[attr]  需要满足两个条件，即使指定的元素E，并且这个元素需要有指定的attr属性。

   li[class]：即是li元素且必须有class属性。

+  E[attr = value]   需要满足两个条件，即使指定的元素E，并且这个元素需要包含指定的attr属性,且属性值必须为指定的value 。

  li[class = red]： 即是li元素且必须包含class属性，且属性值必须为指定的red。

+ E[attr*=value]  需要满足两个条件，即使指定的元素E，并且这个元素需要包含指定的attr属性,且属性值只要包含指定的value字符即可。

   li[class*=red]：即是li元素且必须包含class属性，且属性值需要包含red字符即可。

+  E[attr^=value]   需要满足两个条件，即使指定的元素E，并且这个元素需要包含指定的attr属性,且属性值必须以指定的value字符开头即可

  li[class^=red]: 即是li元素且必须包含class属性，且属性值必须以red字符开头。

+  E[attr$=value]  需要满足两个条件，即使指定的元素E，并且这个元素需要包含指定的attr属性,且属性值必须以指定的value字符结尾即可。

  li[class$=red]：即是li元素且必须包含class属性，且属性值必须以red字符结尾。

#### 03-结构伪类之兄弟伪类选择器

+：获取当前元素之后相邻的满足条件的元素

 ~：获取当前元素的满足条件的兄弟元素

+  span + li： 首先找到span标签，其次找到span标签下面的首个元素且元素类型为li,如果span标签下面的首个元素不为li则样式不起作用。
+  span ~ li： 首先找到span标签，其次span标签下面**所有**相邻的兄弟li元素

#### 04-结构伪类之父级伪类选择器

相对于父元素的结构伪类

+ E:first-child：从E的父元素中找第一个子元素且类型必须是E，如果第一子个元素不是E则查找失败。

  li:first-child：li的父元素中的第一个子li元素。

  注意：1.相对于当前指定元素的父元素。

  ​	    2.查找的类型必须是指定的类型

+  E:last-child: 从E的父元素中找最后一个子元素且类型必须是E，如果最后一个子个元素不是E则查找失败。

   li:last-child：li的父元素中的最后一个子li元素 。

+ E:first-of-type：从E的父元素开始,第一个为E的子元素，如果第一个子元素不为E,则会过滤掉继续查找直到找到第一个为E的子元素为止。

  li:first-of-type：找到li的父元素中的第一个为li的子元素。

+ E:last-of-type：从E的父元素开始,最后一个为E的子元素，如果最后一个子元素不为E,则会过滤掉继续查找直到找到最后一个为E的子元素为止。

   li:last-of-type：找到li的父元素中的最后一个为li的子元素。



+ 指定索引位置 nth-child(从1开始的索引||关键字||表达式)

+ li:nth-child(5)：查找到索引为5的。索引从1开始且不限定子元素类型，如果父元素中有其他类型子元素索引也会计算 。

+ li:nth-child(even)：查找到索引为偶数的子元素。索引从1开始且不限定子元素类型，如果父元素中有其他类型子元素索引也会计算 。

+ li:nth-child(odd)：查找到索引为奇数的，索引从1开始且不限定子元素类型，如果父元素中有其他类型子元素索引也会计算 。

+ li:nth-of-type(even)：产找到索引为偶数的，索引从1开始且严格限定子元素类型，如果父元素中有其他类型子元素索引不会计算 。

+ li:nth-of-type(odd)：产找到索引为奇数的，索引从1开始且严格限定子元素类型，如果父元素中有其他类型子元素索引不会计算 。

+ li:nth-of-type(n):n取值0~子元素的长度，n的值是线性增加的，如果表达式的结果<=0则无效，如果表达式的结果大于子元素的长度，照样起作用。

  表达式例子：

  li:nth-last-of-type(2n)，取到索引为偶数；li:nth-last-of-type(2n+1)，取到索引为奇数。

  li:nth-last-of-type(3n)，取到索引为3的倍数。

  li:nth-last-of-type(-n+3),取到最后3个li元素。

  li:nth-first-of-type(-n+3),取到前面3个li元素。

+ li:empty：代表li的父元素的没有任何内容的子元素，连空格都没有。

####  05-伪元素

普通的双标签都会有before、after，类似input、img等单标签是没有的。

+ ::before：默认在普通标签的左面。
+ ::after：默认在普通标签的右面。
+ content：放置内容的，并且必须是有的。
+ **默认是行内元素**，想设置宽高，转化为块元素，display:block;float、position
+ 如果伪元素需要参照父元素宽高的百分比来设置，那么需要父元素有具体的宽高值。

#### 06-其他伪元素

+ ::first-letter：设置首字母
+ ::first-line：设置文本第一行的样式
+ ::selection：设置当前选中的内容的样式

#### 07-文本阴影的使用

+ text-shadow:2px 1px 1px red;
+ 第一个值：设置文本阴影横向的偏移
+ 第二个值：设置文本阴影纵向的偏移
+ 第三个值：设置文本阴影虚化程度（大小）
+ 第四个值：设置文本阴影的颜色
+ 文本阴影是可以设置多层的，用逗号隔开即可，text-shadow:2px 1px 1px red, 3px 3px 2px blue;

#### 08-盒模型

元素有一个box-sizing属性，是盒子的大小计算模式。

+ 默认情况下box-sizing：content-box;

  这个时候盒子的宽高是 ：内容的宽高 + padding + border。

  此时我们设置的width和height是内容的宽高。

+ box-sizing：border-box

  这种情况下我们设置的width和height是盒模型的宽高。

  然后盒子的宽高是 内容的宽高 + padding + border，所以内容的宽高会自适应发生变化。

#### 09-边框圆角

+ border-radius：10px;这样是设置四个角都有效果

+ border-radius：10px 20px;

  第一个值：左上、右下

  第二个值：右上、左下

+ border-radius：10px 20px 30px;

  第一个值：左上

  第二个值：右上、左下

  第三个值：右下

+ border-radius：10px 20px 30px;

  第一个值：左上

  第二个值：右上

  第三个值：右下

  第四个值：左下

+ 圆：设置圆角的宽高的一半 50%

+ 半圆：高度设置为宽一半，圆角设置，左上和右上即可

#### 11-盒子阴影

+ box-shadow:6px 4px 12px #000；
+ 第一个值：设置盒子阴影横向偏移
+ 第二个值：设置盒子阴影纵向偏移
+ 第三个值：设置盒子阴影的虚化程度
+ 第四个值：设置盒子阴影的范围
+ 第五个值：设置盒子阴影的颜色
+ 第六个值：设置盒子的内阴影
+ 同样也是可以设置多层阴影，还是用逗号隔开


#### 机器人案例

+ 头

  脑袋和眼睛

  脑袋：一个半圆，高度设置为宽度的一般，圆角给左上和右上设置

  眼睛：给脑袋这个元素设置伪元素，左眼睛：before,右眼睛：after

+ 身体

  胳膊和身体

  身体：长方形，左下和右下设置圆角

  胳膊：左胳膊：before，右胳膊：after

+ 腿部

  准备一个元素，设置伪元素即可

  左腿：before，右腿：after












































































































