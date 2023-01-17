#### Javascript

通过defineProps定义props，如:

```ts
const props = defineProps({
    width:{
        type:Number,
        default:350
    },
    progressWidth:{
        type:Number,
        default:0
    }
})
复制代码
```

通过computed方法定义计算属性:

```ts
const styleWidth = computed(() => props.width+'px');
复制代码
```

依然是通过slot标签定义插槽:

```html
<div class="ps-step-container">
    <div class="ps-step-progress"></div>
    <slot></slot>
</div>
复制代码
```

通过defineEmits方法定义事件传递:

- defineEmits注册事件名，方法通常是一个数组，传递多个事件名
- 调用方法的返回值，然后将该事件向上传递

```ts
const emit = defineEmits(["on-click"]);
const changeActive = () => {
    emit("on-click");
}
复制代码
```

通过reactive定义响应式对象，它与ref方法的区别就是，通常我们使用ref方法来定义基本数据类型，而reactive方法则是定义多个对象:

```ts
const bool = ref(false);
const state = reactive({
    status: false,
    list:[
        {
            label:"测试值",
            value:1
        }
    ]
})
复制代码
```

浏览器控制台花式玩法:

```js
console.log("%c " + consoleText,"background:#0ca6dc;padding:4px 10px;border-radius:3px;color:#fff");
复制代码
```

#### less

动态绑定样式变量的写法有两种，第一种则是字符串属性名，第二种则是直接写变量名:

```less
width:v-bind("styleWidth");
width:v-bind(styleProgressWidth);
复制代码
```

::focus-visible选择器，表示键盘伪类焦点选择器，在规范中定义为:元素聚焦，同时浏览器认为聚焦轮廓应该显示。

有时候我们希望键盘触发聚焦轮廓，而鼠标关注焦点则不触发轮廓，此时用以下一行CSS代码搞定。

```css
:focus:not(:focus-visible) {
    outline: 0;
}
复制代码
```

属性选择器语法:

```css
[属性选择器] {
    //CSS样式
}
//如:
[disabled] {
    background-color: @color;
    color: @font_color;
    cursor: not-allowed;
}
复制代码
```

其它知识点同前面示例。

