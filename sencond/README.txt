	第一个：是用HTML5实现的，在页面中拖到指定的方块中去，并能在两个方块中来回拖拽。
	第二个：从外部拖拽一张图片到指定的方块中去；
	第三个：在网页上任意区域内任意拖拽；
	第四个：我模拟了百度首页的登录界面做的一个浮动的登录界面。
从这四个demo一步步深入体会到鼠标拖拽效果的神奇的魅力。

具体实现：
HTML5实现：
1.	设置元素可拖放，draggable=“true”
2.	DataTransfer，拖拽对象用来传递的媒介
Drag & Drop 包括以下事件：
	dragstart：要被拖拽的元素开始拖拽时触发，这个事件对象是被拖拽元素
	dragenter：拖拽元素进入目标元素时触发，这个事件对象是目标元素
	dragover：拖拽某元素在目标元素上移动时触发，这个事件对象是目标元素
	dragleave：拖拽某元素离开目标元素时触发，这个事件对象是目标元素
	dragend：在drop之后触发，就是拖拽完毕时触发，这个事件对象是被拖拽元素
	drop：将被拖拽元素放在目标元素内时触发，这个事件对象是目标元素
js实现：
1.	事件onmousedown鼠标按下，onmousemove鼠标移动，开始拖动。
所以我们要获取鼠标的坐标，document.onmousemove。设置event对象来获取事件（ev=ev||window.event）让ev在所有浏览器下获取event事件。并且设置了onmousedown和onmouseup来接受doucument.onmousemove
2.	Onmouseup，停止拖动；
3.	计算出拖动的距离
在拖动的时候，我们要先计算拖动对象的相对于屏幕的上下方距离
