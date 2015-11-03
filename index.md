#知识点巩固

##JS & css & HTML
- 兼容性

	BOM:[IE6兼容性BUG](./ie-compatible-summary.md)
	
	DOM&EVENT:[js兼容性方法](./js-compatible-function.md)
- 面向对象
    
- 闭包[Javascript进阶-闭包](./javascript-closure.md)


##重要api
- 数组的api

    1.静态方法 
        
        方法:                    大概作用(是否改变原数组)  返回
        Array();                创建数组                数组
        new Array               实例化                  数组
        Array.isArray(a);       判断数组                布尔值
    2.原型方法
    
        方法:                    大概作用(是否改变原数组)  返回
        valueOf()               构造函数                数组本身
        toString()              数组字符串               字符串
        push()                  从尾部添加数组元素(改)    数组长度
        unshift()               从头部添加数组元素(改)    数组长度
        pop()                   从尾部弹出数组元素(改)    弹出元素
        shift()                 从头部弹出元素(改)       弹出元素
        join()                  将数组拼接成字符串        字符串
        concat()                连接数组                新数组
        reverse()               逆序(改)                新数组
        slice()                 截取数组                新数组
        splice()                删除元素(改)            删除的数组
        sort()                  排序(改)               新数组
        
        map()                   遍历数组               return的值
        forEach()               遍历数组(可改)          undefined
        filter()                过滤器                 新数组
        some()                  断言至少一个            布尔值
        every()                 断言全体元素            布尔值
        reduce()                累计                   累计结果
        reduceRight()           从右累计                累计结果
        indexOf()               查找                   位置|-1
        lastIndexOf()           倒序查找                位置|-1
        
           
    3.数组对象属性
        
        length
        
        
- 字符串的API
    1.静态方法
    
        方法:             大概作用(是否改变原字符串)        返回    
        String()          转字符串                       字符串
        new String()      创建字符串对象                 类数组对象
        fromCharCode()    根据Unicode编码生成字符串        字符串
        
    2.原型方法
        
        方法:             大概作用(是否改变原字符串)        返回 
        charAt()          获取某位置元素                  字符串
        charCodeAt()      获取莫位置元素对应Unicode码     Number
        concat()          连接字符串                    新字符串
        substring()       按两个位置截取字符串            截取的字符串
        substr()          按一个位置和长度截取字符串       截取的字符串
        slice()           按两个位置截取字符串            截取的字符串
        indexOf()         判断元素存在位置                 位置|-1
        lastIndexOf()     从后判断元素存在位置              位置|-1
        trim()            去首尾空格                      新字符串
        toLowerCase()     小写                           新字符串
        toUpperCase()     大写                           新字符串
        localeCompare()   比较字符串顺序大小               -1|0|1
        match()           匹配                           匹配数组  
        search()          查找                            位置|-1
        replace()         替换                            新数组
        split()           分割字符串为数组                  数组
        
    3.字符串属性
    
        length


- 字符串数组都有的API
        
        length
        concat()
        slice()
        indexOf()
        lastIndexOf()
        
##移动端
- css3
    - css3选择器 [css3选择器](./css3-selector.md)
	- css3属性 [CSS3新增属性](./css3-new-attribute.md)
	- 媒体查询 
	
	    ```
	    @media screen and (min-width:400px) and (max-width:500px) 
	    {.box {margin: 0 auto;}}
	   

	    @media screen and(min-width:500px) 
	    {.box {margin: 20px auto;}}
	    ```
	- 关键帧
	
	    ```
	    @-webkit-keyframes rotate{
	        0%{
	            -webkit-transform:rotate(0deg);
	        }
	        100%{
	            -webkit-transform:rotate(180deg);
	        }
	    }
	    ```
	    - 要配合animation使用
	    
	      `-webkit-animation:1s rotate[关键帧] infinite[是否无限运动] alternate[是否奇数偶数次反向运动] linear[线性运动];`
	
- h5
    - h5的本地存储，永久存储，使用方式和各自的区别
    
    
- 移动端常见布局方式
    - 百分比
    - rem
    - 流体



##常见算法
- 枚举
- 冒泡

    复杂度o(n^2)

    ```
    function sort(array, compareFn){
        compareFn = compareFn||function(item1, item2){ return item1.localeCompare(item2);};
            
        for(var i= 0,len = array.length; i<len; i++){
            for(var j = i,length = array.length; j<length; j++){
                if(compareFn(array[i], array[j]) > 0){
                        var t = array[i];
                        array[i] = array[j];
                        array[j] = t;
                    }
                }
            }
            return array;
        }
        
    ```

- 选择
- 插入
- 快排

    复杂度o(logn)
    
    ```
    function quickSort(arr){
		if(arr.length<=1){
			return arr; //空数组和单元素数组直接返回
		}
		var num=Math.floor(arr.length/2);//先找到数组的中间位置
		
		var numValue=arr.splice(num,1)[0];//用splice方法取出这个值
		//alert(numValue);
		var left = [];
		var right =[]; //创建两个数组用于存放大于中间值和小于中间值的数。
		for(var i = 0;i<arr.length;i++)
		{
			if(arr[i]>numValue)	
			{
				right.push(arr[i]);//大于中间值的放右边
			}
			if(arr[i]<=numValue)
			{
				left.push(arr[i]);//小于中间值的放左边
			}
		}

		//return left.concat(numValue,right);
		return quickSort(left).concat(numValue,quickSort(right));
		//将左和右数组继续快排然后拼接。 递归方法
	}
    ```
- 对应时间复杂度




##常见布局 

		一端固定宽度，另一端自适应………还有两端固定宽度，中间自适应的三栏布局

		水平和垂直居中
		对于没有给定宽度和高度的div如何实现垂直，水平居中…

- 清楚浮动的常见方式和原理，比如给设置overflow:hidden为什么可以清楚浮动

##前端优化

		网络  dom  js
