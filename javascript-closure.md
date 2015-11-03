#Javascript进阶-闭包
##1.什么是闭包

函数嵌套函数，内部函数可以引用外部的参数和变量，参数和变量不会被垃圾回收机制所收回，外部函数最终返回内部函数的函数名。

从垃圾回收机制来看，一个闭包就是当一个函数返回时，一个没有释放资源的栈区。

例如：

```
    function test(num){
		var sum=5;
		function alertSum(){
			sum+=num;
			alert(sum);
		}
			return alertSum;
	}
	var a=test(5);
	a();//10		
```
	
	
##2.闭包的作用，应用在哪里
- 好处

    1.希望一个变量长期驻扎在内存中
    
    2.避免全局变量的污染
    
    3.私有成员的存在，保护内部变量不被外部调用

		
- 实际用法：

	1.模块化代码，减少全局变量污染。
	
	```
	(function(){
	    //模块化代码
	})()
	```
	
    2.在循环中不用设置index直接找到对应元素的索引。
    
    ```
    var aBtn = document.getElementsByTagName('button');
    for(var i = 0; i < aBtn.length; i++){
        (function(i){
            aBtn[i].onclick=function(){
                //do something
            }
        })(i);
    }
    
    ```

- 闭包需要注意的地方
	
	IE避免内存泄漏
	
	例如：
	
	```
	function closureTest(){
		var testDiv=document.getElementById('div1');
		testDiv.onclick=function(){
			testDiv.style.left=100+'px';
		}
	}
	```
		
	closureTest方法创建了一个内部匿名函数，由于testDiv的onclick
	属性引用了该匿名函数，testDiv是一个外部对象，所以该匿名函数会在
	内存中保存。
	
	而该函数所要用的testDiv对象也一直保存在内存中。
	(本来的意愿是不希望testDiv长久保留的)
	这样就形成了内存泄漏。

	解决办法：
	
	利用
	
	`window.onunload=function(){ testDiv.onclick=null; }`
	
	结束循环引用。
