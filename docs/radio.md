# radio组件

----------

<h2 id="cid_0">说明</h2>

radio组件主要用于单项选择，radio除了自己的状态样式外，开发者还可以自己设置图片当做状态样式，该组件可作为表单控件使用。该组件封装了change事件，只要该控件内部定义的属性发生变化都会触发该事件（用户自己写的属性改变不会触发change事件）。  

用法：在js里面引入require("radioUI");  

示例：如果需要让radio之间相互排斥需要设置group属性，并且值要求一样。  

  
```html
<radio  group="radiotest"   caption="女"  />
<radio  group="radiotest"   id="radio_test" checked="false" caption="男" style="checked-color:red;"/>

``` 

<h2 id="cid_1">属性</h2>


本节目录：

> [公共属性](#sx_0)	
> 
> [checked	选择状态](#sx_1)
>
>[group	radion组](#sx_2)
>
>[caption  文字内容（可以通过js修改）	](#sx_3)
>
>[checkedimage	选中状态的图片路径](#sx_4)
>
>[nocheckedimage	未选中状态的图片路径](#sx_5)
>
>[readonly	是否只读（可以通过js修改）](#sx_6)
>
>[value  提交值](#sx_7)



<span id="sx_0">**公共属性**</span>  

[参见公共属性章节](https://gitdocument.exmobi.cn/sprite-api/ggsx.html)，包括：id、style、class；

<span id="sx_1">**checked**</span>

<code>选择状态</code>

true选中，false 未选中(通过js可以修改)

**注： **  通过js设置checked如果存在同组的radio不具备排斥性，如需通过js控制可以调用click()方法，模拟radio点击；不写默认false。


<span id="sx_2">**group**</span>

<code>radion组</code>

radion组，同组的radion选择状态排斥


<span id="sx_3">**caption**</span>

<code>文字内容</code>

文字内容(通过js可以修改)



<span id="sx_4">**checkedimage**</span>

<code>选中状态的图片路径</code>

选中状态的图片路径，设置后默认选中样式失效



<span id="sx_5">**nocheckedimage**</span>

<code>未选中状态的图片路径</code>

未选中状态的图片路径，设置后默认未选择样式失效


<span id="sx_6">**readonly**</span>

<code>是否只读</code> 

是否只读，取值true和false，不写默认false；(通过js可以修改)；



<span id="sx_7">**value**</span>

<code>提交值</code> 

用于记录需要提交的值

<h2 id="cid_2">样式</h2>

[参见公共样式章节](https://gitdocument.exmobi.cn/sprite-api/ggys.html)，包括：  

> 尺寸：height默认30;
> 
> 定位
> 
> 内边距
> 
> 外边距
> 
> 边框
> 
> 背景
> 
> flexbox布局：align-self，flex

**color**	

<code>文字颜色</code>

文字颜色(通过js可以修改); 默认#000000
	
**height**	

<code>radio的高度</code>

radio图标的高度(通过js可以修改); 设置后图标的高宽同时生效，一定保证是正方形或者圆形。默认30dp
	
**font-size**	

<code>字体大小</code>

字体大小(通过js可以修改)；默认16dp	

**readonly-radius**	

<code>只读状态遮罩区域的弧度</code>

只读状态遮罩区域的弧度，一般用于有图片的时候设置，比如如果用的图片是圆形为了保证效果只读状态下遮罩区域也是圆形可以设置该值,默认0	

**checked-color**	

<code>checked时候的背景色</code>

checked时候的背景色; 默认#549FF7；

**nochecked-color**	

<code>未选中状态下背景色(</code>

未选中状态下背景色(对于radio效果在边框上)；默认#9B9C9C；



<h2 id="cid_3">js方法</h2>


**公共方法**  

[事件相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_0)，包括：

> [on(messageName:string,callback:Function): void   组件注册事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_1)   
> 
> [fire(messageName:string,params:Array&lt;any&gt;): void  组件事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_2)   
> 
> [off(messageName:string,callback:Function): void  组件移除事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_3)  
>  
> [getOn(messageName:string): Array&lt;Function&gt;  获取已绑定的事件的触发函数](https://gitdocument.exmobi.cn/sprite-api/ggff.html#jjxg_4)   

[动画相关](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_1)，包括： 
 
> [startAnimation(jsonData:Object,callback:Function): void  启动UI组件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_1)   
> 
> [startAnimator(jsonData:Object,callback:Function): void  启动UI组件属性动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_2)   
> 
> [startKeyFrameAnimator(jsonData:Object,callback:Function): void  启动UI组件关键帧动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_3)  
>  
> [ releaseAnimator(): void  结束控件动画](https://gitdocument.exmobi.cn/sprite-api/ggff.html#dhxg_4)   

[尺寸和位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_2)，包括：  

> [getFrame(): Object  获取组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_1)   
> 
> [setFrame(frame:Object): void  设置组件在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_2)   
> 
> [getCenter(): Object  获取组件中心点在父容器中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_3)  
>
> [getAbsoluteFrame(): Object  获取组件在绘制窗口中的位置](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cchwz_4)   


[普通Dom节点操作](https://gitdocument.exmobi.cn/sprite-api/ggff.html#cid_3)，包括：  

> [getParent(): IElement  获取父节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_1)   
> 
> [getNext(): IElement  获取同级下一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_2)   
> 
> [getPrevious(): IElement  获取同级前一个节点](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_3)  
> 
> [remove(): void  从父容器中移除自身](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_4)  
> 
> [clone(isDeep:boolean):IElement  对当前Dom节点进行克隆](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_5)  
>
> [setAttr(attrName:string,attrValue:string): void  设置节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_6)   
>
> [getAttr(attrName:string):string  获取节点属性值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_7) 
>
> [getAttrs(): Object  获取节点所有属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_8) 
>
> [removeAttr(attrName:string): void  移除节点属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_9) 
>
> [hasAttr(attrName:string): boolean  节点是否具有该属性](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_10) 
> 
> [setStyle(styleName:string,styleValue:string): void  设置节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_13)  
>
> [getStyle(styleName:string):string  获取节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_14)   
>
> [clearStyle(styleName:string): void  移除节点样式值](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_15)    
>
> [setClassStyle(className:string,domobj:IElement): void   设置节点对应Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.htm#ptdom_16) 
>  
> [getClassStyle(): string  获取节点已设置Class样式](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_17)  
>  
> [getTag(): string  获取UI组件类型](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_18)  
>  
> [getId(): string  获取UI组件Id标识](https://gitdocument.exmobi.cn/sprite-api/ggff.html#ptdom_19) 


**click():void**

<code>模拟点击一次radio</code>

模拟点击radio组件，执行click()方法，相当于手动点击了一下radio

参数：无

返回值：无


**bindDom(domobj:IElement):void**

<code>绑定一组radio所在的容器的dom</code>

如果不执行此方法，组件内部默认从uixml的根节点开始寻找同组的radio

**注：** 在模板里面使用radio，必须执行该方法，传入radio组所在的容器dom.

参数：

domobj: 容器的dom对象

返回值：无



<h2 id="cid_4">事件</h2>


**change**  

<code>监听radio属性改变</code>

event对象包括：  
 
type：事件类型，字符串类型，固定值：change；  

target：触发事件的目标组件，dom对象；  

timestamp：事件触发的时间戳,单位毫秒，数字类型；

<h2 id="cid_5">示例</h2>

```html
<page>
    <script>
        <![CDATA[
        var window = require("Window");
        var document = require("Document");
        var console = require("Console");
        var ui = require("UI");
        var ListAdapter = require("ListAdapter");
        var console = require("Console");
        require("titlebarUI");
        require("buttonUI");
        require("radioUI");
        var myappjs = require("myapp");
        var screenWidth = window.getScreenWidth();
        window.on("animator", function () {
            var setradio = document.getElement("setradio");
            var getradio = document.getElement("getradio");
            var creatradio = document.getElement("creatradio");
            var radio_test = document.getElement("radio_test");
            var clickradio = document.getElement("clickradio");
            setradio.on("click", function (e) {
                var checked = radio_test.getAttr("checked");
                if (checked == "true") {
                    radio_test.setAttr("checked", "false");

                }
                else {
                    radio_test.setAttr("checked", "true");
                }

            });

            getradio.on("click", function (e) {
                myappjs.alert(radio_test.getAttr("checked"));
            });

            radio_test.on("change", function (e) {
                myappjs.alert(radio_test.getAttr("checked"));
            });

            clickradio.on("click", function (e) {
                var radio1 = document.getElement("radio1");
                radio1.click();
            });

            var i = 9;
            creatradio.on("click", function (e) {
                var jsonattr = {};
                jsonattr.id = "radio_" + i;
                i = i + 1;
                jsonattr.caption = "小米5";
                jsonattr.group = "radioname";
                var radiodom = document.createElement("radio", jsonattr);
                radiodom.setStyle("checked-color", "red");
                //console.log(radiodom);
                var radiobox1 = document.getElement("radiobox1");
                radiobox1.appendChild(radiodom);
                document.refresh();

            });

            var testreadonlybutton = document.getElement("testreadonlybutton");
            var testreadonly2 = document.getElement("testreadonly2");
            var testreadonly = document.getElement("testreadonly");
            testreadonlybutton.on("click", function (e) {

                if (testreadonly.getAttr("readonly") == "true") {

                    testreadonly.setAttr("readonly", "false");
                    testreadonly2.setAttr("readonly", "false");
                }
                else {
                    testreadonly.setAttr("readonly", "true");
                    testreadonly2.setAttr("readonly", "true");

                }
            });
            //titlebar关闭页面
            var title = document.getElement("title");
            title.on("liconClick", function (e) {
                var json = {};
                window.close(json);

            });
        });
	
    ]]>
    </script>
    <style>
        @import url(res:sprite_component/css/sprite.layout.css);
        @import url(res:sprite_component/css/sprite.color.css);
        radio {
            margin: 5;
        }        
        button {
            margin: 8;
            border-radius: 8;
        }
    </style>
    <ui>
        <box class="white full" id="box">
            <titlebar title="radio控件" class="titlebar-hasstatus" licon="res:yuanhongqian/image/icon.png" style="licon-width:24;licon-height:24"
                id="title" />
            <scroll style="flex:1;width:fill_screen;font-size:12;">
                <box style="flex-direction:row;flex-wrap:wrap;align-items:flex-start;width:fill_screen;">
                    <radio group="radiotest" caption="女" />
                    <radio group="radiotest" id="radio_test" checked="false" caption="男" style="checked-color:red;" />

                    <button value="设置radio" id="setradio" />
                    <button value="得到radio" id="getradio" />

                    <radio caption="男" style="checked-color:blue;height:50;font-size:30" />
                    <radio checked="true" caption="男" style="checked-color:blue;height:20;color:red" />
                    <radio checked="true" caption="" style="checked-color:blue;height:30;color:red" />

                    <button value="创建radio" id="creatradio" />
                    <button value="模拟点击radio" id="clickradio" />
                </box>
                <box id="radiobox1" style="flex-direction:row;flex-wrap:wrap;align-items:flex-start;width:fill_screen;background-color:#dddddd">
                    <radio id="radio1" group="radioname" caption="三星" style="" />
                    <radio id="radio2" checked="true" group="radioname" caption="iphone" style="checked-color:#F8BF53;" />
                    <radio id="radio3" group="radioname" caption="华为" style="checked-color:#F8BF53;" />
                    <radio id="radio4" group="radioname" caption="小米" style="checked-color:#F8BF53;" />
                    <radio id="radio5" group="radioname" caption="小米2" style="checked-color:#F8BF53;" />
                    <radio id="radio6" group="radioname" caption="小米3" style="checked-color:#F8BF53;" />
                    <radio id="radio7" group="radioname" caption="小米4" style="checked-color:#F8BF53;" />
                    <radio id="radio8" group="radioname" caption="小米5" style="checked-color:#F8BF53;" />
                </box>
                <box style=";background-color:yellow;flex-direction:row;flex-wrap:wrap;align-items:flex-start;width:fill_screen;">
                    <radio checkedimage="res:yuanhongqian/image/rad_pressed.png" nocheckedimage="res:yuanhongqian/image/rad_normal.png" group="radioname2"
                        caption="足球" style="checked-color:#F8BF53;height:40" />
                    <radio checkedimage="res:yuanhongqian/image/rad_pressed.png" nocheckedimage="res:yuanhongqian/image/rad_normal.png" group="radioname2"
                        caption="篮球" style="checked-color:#F8BF53;" />
                    <radio checkedimage="res:yuanhongqian/image/rad_pressed.png" nocheckedimage="res:yuanhongqian/image/rad_normal.png" group="radioname2"
                        caption="橄榄球" style="checked-color:#F8BF53;" />
                    <radio checkedimage="res:yuanhongqian/image/rad_pressed.png" nocheckedimage="res:yuanhongqian/image/rad_normal.png" group="radioname2"
                        caption="兵乓球" style="checked-color:#F8BF53;" />
                </box>
                <radio id="testreadonly" caption="不带图片" />
                <radio id="testreadonly2" style="readonly-radius:15" checkedimage="res:yuanhongqian/image/nme-active.png" nocheckedimage="res:yuanhongqian/image/nme.png"
                    caption="带图片" />
                <button value="设置readonly属性" id="testreadonlybutton" />
            </scroll>
        </box>
    </ui>
</page>
```

>代码效果图： 

<img width="250" src="image/fengzhuangzhujian_14.png" style="width:250;"/> 