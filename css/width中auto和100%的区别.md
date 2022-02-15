1.首先默认不写width的话,就是auto

2.width;100% 的作用在于直接继承父盒子的宽度,真的是直接继承



父盒子宽1000px(也许有padding,有margin,有border)

但是子元素得到的宽度还是1000px,不会有损耗的

子元素设置的border,margin和padding是在定宽的条件下进行变化的



3.width:auto中,父元素1000px,要减去父元素自己的padding100px,因为padding不允许放content,然后子元素如果自己设置了外边距100px margin.border ,padding,统统都要减去,最后剩下来的是允许使用的content区,也就是最后得到的width

600px



margin甚至能设置负值

