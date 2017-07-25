## 表单操作
在form中，label的作用： 标签用来关联归属表单。 <br>
而可关联元素：<br>**button,fieldset,input,keygen,label,object,output,select,textarea。**
>需要注意的是，每个元素中对应form的值都是浏览器自己算的，所以是一个只读属性，不可在程序过程中进行修改。  

如果要修改关联元素所归属的表单，我们则可以修改元素的form属性，来调整元素所归属的表单，如下例子：
> `label.setAttribute('form','newFormId');`

###input
---
* type
	* 控件外观
	* 数据类型
	* 默认为text
* 本地图片预览
	* onchange
	* accept
	* multiple
	* files

> `<input type="file" accept="image/*" multiple/>`

* **accept可接受的字符串**
	* audio/*（音频）
	* video/*（视频）
	* image/*（图片）
	* 不带";"的MIME type
	* 以“.”开始的文件后缀名
	
有多个类型可以用逗号分隔

```js
file.addEventListener(
	'change',function(event){
		var files = Array.prototype.slice.call(
			event.target.files,0
		);
		files.forEach(function(item){
			file2dataurl(item,function(url){
			var image = new Image();
			parent.appendChild(image);
			image.src = url;
			});
		});
	}
);
```



