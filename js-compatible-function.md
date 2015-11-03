#JS兼容性方法
##事件
- 事件对象兼容

	    ie/chrome : event是一个内置全局对象
	    标准下 : 事件对象是通过事件函数的第一个参数传入

	    兼容写法 :   ev = ev||event;
	    
- 取消事件冒泡兼容

        IE8:    cancelBubble = true;
        非IE:    ev.stopPropagation();
- 阻止默认事件

        IE8:    在事件方法尾部 return false;//注意该方法还会阻止冒泡
        非IE:    ev.preventDefault();
- 事件监听兼容

    ```
    function bindEvent(obj,event,callback){
	    if(obj.addEventListener){
		    //标准下
	    	obj.addEventListener(event,callback,false);
    	}else{
		    //非标准下
	    	obj.attachEvent('on'+event,function(){	
	    		callback.call(obj);
	    	});
    	}
    }

    ```

##DOM
- children属性

		元素.children : 只读 属性 子节点列表集合

		标准下：只包含元素类型的节点
		非标准下：只包含元素类型的节点,ie7以下不会包含非法嵌套子节点
		
- parent节点读取方法
		
		元素.parentNode : 只读 属性 当前节点的父级节点 兼容性很好
		元素.offsetParent : 只读 属性 离当前元素最近的一个有定位属性的父节点
		该属性判断父级的几个点：
		如果没有定位父级，默认是body
		ie7以下，如果当前元素没有定位默认是body，如果有定位则是html
		ie7以下，如果当前元素的某个父级触发了layout，那么offsetParent就会被指向到这个触发了layout特性的父节点上

		Layout是ie7以下特性 
		是否有Layout特性 ：	
		doucument.getElementById('').currentStyle.hasLayout;
		//true:有 false:没有	alert(document.getElementById('div2').currentStyle.hasLayout );
		
- 判断所选元素到body的距离：

	```
	function getPos(obj)
	{
		var pos={left:0,top:0};
		while(obj)
		{
			pos.left += obj.offsetLeft;
			pos.top += obj.offsetTop;
			obj=obj.offsetParent;
		}
		return pos;

	}
	```
	

- 滚动条距离

    ```
    //滚动条滚动距离
	document.documentElement.scrollTop //非chrome
	document.body.scrollTop //chrome
	//兼容性方案
	var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
    ```
    
- 获取行间样式

    ```
    function getStyle(obj,name){
        if(obj.currentStyle){
            //IE
            return obj.currentStyle[name];
        }else{
            //标准
            return getComputedStyle(obj,false)[name];
        }
    }
    ```
    
##AJAX
    ```
        function ajax(method, url, data, successFn){

		    url = (method === 'get') && data ? url+'?'+data : url;
		    new xhr = null;
		    try {
		    	xhr = new XMLHttpRequest();
		    } catch (e) {
			    xhr = new ActiveXObject('Microsoft.XMLHTTP');
		    }
		
	    	xhr.open(method,url,true);

		    if( method === 'get' ){
			    xhr.send();
	    	}else{
		    	xhr.setRequestHeader('content-type','application/x-www-form-urlencode');
			    xhr.send(data);
		    }

		    xhr.onreadystatechange = function(){
			    if( xhr.readyState == 4){
				    if(xhr.status === 200){
					    successFn&&successFn(xhr.responseText);
				    }else{
					    alert( '出错了，Err:' + xhr.status + '错误');
				    }
			    }
		    }

	    }
    ```