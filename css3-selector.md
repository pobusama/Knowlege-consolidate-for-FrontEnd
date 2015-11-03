#CSS3选择器 
##属性选择器

           
-  标签[属性]{}   使用属性名，但没确定任何属性值

-  标签[属性="属性值"]{}   指定属性名，并指定了该属性的属性值

-  标签[属性~="value"]{}  指定属性名，并且具有属性值，此属性值是一个词列表，并且以空格隔开，其中词列表包涵了"value"而且等号前的~不能不写

-  标签[属性^="value"]{}  指定了属性名，并且有属性值，属性值是以value开头的

-  标签[属性$="value"]{}  指定了属性名，并且有属性值，属性值是以value结尾的

-  标签[属性*="value"]{}  指定了属性名，并且有属性值，属性中包含了value值的
  
-  标签[属性|="value"]{}  指定了属性名，并且属性是以value或者value-开头的值
	       
##结构选择器
	    
- 标签:nth-child(1) 指定标签元素的父级下的第1个子节点，这个节点还必须是指定标签        (如果不是指定标签，就不起作用)

- 标签:nth-child(odd) 指定标签元素的父级下的奇数子节点，这些节点还必须是指定标签

- 标签:nth-child(even) 指定标签元素的父级下的偶数子节点，这些节点还必须是指定标签

- 标签:nth-child(n) 指定标签元素的父级下的0~无穷大子节点，可计算(如2n、2n-1、3n)，这些节点还必须是指定标签
- body *:nth-child(2) body的第二个子节点(任何标签)

- 标签:nth-last-child(1) 效果等同于 p:nth-child(1)，只是从后往前数

- p:nth-of-type(2) 找p标签父级下，第二个p元素 同样有p:nth-last-of-type(2)

- p:first-child 等同于 p:nth-child(1)

- p:last-child 等同于 p:nth-last-child(1)

- p:first-of-type 等同于 p:nth-of-type(1)
	
- p:last-of-type 等同于 p:nth-last-of-type(1)

- p:empty 找到p标签父级下所有空的p标签

- p:only-of-type 找到p标签父级下仅有一个的p标签(可以有别的标签的子节点存在)

- p:only-child  找到p标签父级下仅有一个子节点，这个子节点还必须是p标签(不能有别的子节点存在)

##伪类和伪元素
- E:target 表示当前的URL片段的元素类型，这个元素必须是E，target代表的是锚的
	哈希值对应的元素

- E:disabled 表示不可点击的表单控件

- E:enabled 表示可点击的表单控件

- E:checked 表示已选中的checkbox或radio

- E~F:表示E元素后面相邻的F元素

- E:first-line 表示E元素内部文本的第一行 

- E:first-letter 表示E元素内部文本的第一个字符
	(用这个选择符设置样式以后这个字不能被选中)

- E::selection 表示E元素内在用户选中文字时，选中的文字的样式

- E::before 在E元素内部内容前生成内容 如E::before{content:"1213"}

- E::after 在E元素内部内容后生成内容

- E:not(S) 表示选择所有E元素，排除这些元素中的S元素



	        
	     