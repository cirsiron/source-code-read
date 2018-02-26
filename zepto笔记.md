### zepto 源码笔记 
1. 为了保证undefined一定是undefined，可以直接设置var undefined;

2. fragment的实现：如何把一段html字符串转换为元素
    - 原理就是创建一个元素包裹，将html字符串方法包裹元素中，转换为元素后，然后再取出里面的子元素;
```
//源码示例
var container = document.createElement("div");
function fragment(html) {
    container.innerHTML = (''+html).trim();
    var result = slice.call(container.childNodes);
    container.innerHTML = "";
    return result;
}
```
3. 默认的函数可设置一个空的不用重复设置
```
function empty() {}
```
4. 尽量少些匿名函数
5. 合理的使用try{} catch(e){}
6. 如果对浏览器进行类型判断时，detect模块正则match匹配，可以直接拿到类型和版本。
```
 // 简写版
function detect(userAgent) {
    var ua = userAgent,
    os= {},
    android = ua.match(/(Android)\s+([\d.]+)/);
    if(android) {
        os.android = true,os.android = android[2]    }
    return os;
}
```
7. 
