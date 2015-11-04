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



   1.h5的本地存储:永久存储，使用方式和各自的区别
    
    HTML5 定义了本地存储规范 Web Storage ， 提供了两种存储类型 API  **sessionStorage **和 **localStorage**，二者的差异主要是__数据的保存时长__及__数据的共享方式__。
    - 生命周期
        - localStorage 一直存储在本地，数据存储是永久的，除非用户或程序对其进行删除操作；
        - sessionStorage在会话期内有效，数据在浏览器关闭后自动删除；
    - 作用范围
        - localStorage是基于域的，任何在该域内的页面都可以访问
        - sessionStorage在保存它的窗口，和由当前窗口创建的新窗口有效，直到相关联的标签页关闭
    - 和cookie的区别
        - cookie在浏览器和服务器间来回传递， sessionStorage和localStorage不会；
        - sessionStorage和localStorage的存储空间更大，有更多丰富易用的接口，各自独立的存储空间；
        
    - Web Storage API
        - localStorage.length ：一个只读的 length属性。 可以知道 localStorage 中存储着多少条数据
        - localStorage.setItem(key, val)：存储一条数据
        - localStorage.getItem(key)：通过 key 获取该条数据
        - localStorage.removeItem(key)：删除一条数据 
        - localStorage.clear()：清空所有 key/value 键值对 items
        - sessionStorage同localStorage
    - Storage 事件监听
        - 事件名：storage
        - key 表示属性中的键名。
        - oldValue 更新前的键值。
        - newValue 数据更新后的键值。
        - url 记录 Storage 事件发生时的源地址。
        - StorageArea 指向事件监听对应的 Storage对象
- 移动端常见布局方式
    - 百分比
    - rem
        
        ```
        var clientW = document.documentElement.clientWidth;
	    var oHtml = document.getElementsByTagName('html')[0];
	    oHtml.style.fontSize = clientW/3+'px';
	    ```
    - 流体



##常见算法

- 冒泡

    复杂度o(n^2)

    ```
    function swap(myArray, p1, p2){
        var temp = myArray[p1];
        myArray[p1] = myArray[p2];
        myArray[p2] = temp;
    }    
    function bubbleSort(myArray){

        var len = myArray.length,
            i, j, stop;

        for (i=0; i < len; i++){
            for (j=0, stop=len-i; j < stop; j++){
                if (myArray[j] > myArray[j+1]){
                    swap(myArray, j, j+1);
                }
            }
        }

        return myArray;
    }    
    ```

- 选择
    复杂度：o(n^2)
    
    ```
    function selectionSort(myArray){

        var len = myArray.length,
        min;

        for (i=0; i < len; i++){

            // 将当前位置设为最小值
            min = i;

            // 检查数组其余部分是否更小
            for (j=i+1; j < len; j++){
                if (myArray[j] < myArray[min]){
                    min = j;
                }
            }

            // 如果当前位置不是最小值，将其换为最小值
            if (i != min){
               swap(myArray, i, min);
            }
        }

        return myArray;
    }
    ```
- 插入

    复杂度：O(n^2)
    
    ```
    function insertionSort(myArray) {

        var len = myArray.length,     // 数组的长度
        value,                      // 当前比较的值
        i,                          // 未排序部分的当前位置
        j;                          // 已排序部分的当前位置
    
        for (i=0; i < len; i++) {
            // 储存当前位置的值
            value = myArray[i];
        
            /*
             * 当已排序部分的当前元素大于value，
             * 就将当前元素向后移一位，再将前一位与value比较
             */
            for (j=i-1; j > -1 && myArray[j] > value; j--) {
                myArray[j+1] = myArray[j];
            }

            myArray[j+1] = value;
        }
    
        return myArray;
    }
    ```
- 合并排序

    复杂度：o(nlogn)

    
    ```
    function merge(left, right){
        var result  = [],
            il      = 0,
            ir      = 0;

        while (il < left.length && ir < right.length){
            if (left[il] < right[ir]){
                result.push(left[il++]);
            } else {
                result.push(right[ir++]);
            }
        }

        return result.concat(left.slice(il)).concat(right.slice(ir));
    }
    
    function mergeSort(myArray){

        if (myArray.length < 2) {
           return myArray;
        }

        var middle = Math.floor(myArray.length / 2),
           left    = myArray.slice(0, middle),
           right   = myArray.slice(middle);

           return merge(mergeSort(left), mergeSort(right));
    }
    ```
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




##常见布局 

		一端固定宽度，另一端自适应………还有两端固定宽度，中间自适应的三栏布局

		水平和垂直居中
		对于没有给定宽度和高度的div如何实现垂直，水平居中…

- 清除浮动的常见方式和原理，比如给设置overflow:hidden为什么可以清楚浮动
    - 原因
        
        在CSS规范中，浮动定位不属于正常的页面流（page flow），是独立定位的。所以，只含有浮动元素的父容器，在显示时不考虑子元素的位置，就当它们不存在一样。这就造成了显示出来，父容器好像空容器一样。
    
    - overflow:hidden
    
        父元素设置overflow:hidden可以清除浮动
        - 原理：让父容器变得可以自动"清理"（clearing）子元素的浮动，从而能够识别出浮动子元素的位置，不会出现显示上的差错。
        - 缺点：一个是IE 6不支持，另一个是一旦子元素的大小超过父容器的宽度，就会出显示问题。
    - after 伪类
    
        ```
        .clearfix:after{
            content:"";
            clear:both;
            display:block;
        }
        .clearfix{
            zoom:1;
        }
        ```
        - 原理：添加一个不含浮动的子元素，而这个元素又排在浮动子元素的后面，这样做可以让父级识别出浮动元素位置，从而留出浮动元素的位置。
        
        "clearfix"是父容器的class名称，"content:"020";"是在父容器的结尾处放一个空白字符，"height: 0;"是让这个这个空白字符不显示出来，"display: block; clear: both;"是确保这个空白字符是非浮动的独立区块。
        
        - 问题：
        
        :after选择符IE 6不支持，也就是说上面的这段代码在IE 6中无效，这怎么办？
我们添加一条IE 6的独有命令"zoom:1;"就行了，这条命令的作用是激活父元素的"hasLayout"属性，让父元素拥有自己的布局。IE 6会读取这条命令，其他浏览器则会直接忽略它。

     - layout说明
     
         IE使用Layout概念来控制元素的尺寸和位置。如果一个元素有Layout，它就有自身的尺寸和位置；如果没有，它的尺寸和位置由最近的拥有布局的祖先元素控制。
        
##前端优化

		网络  dom  js
