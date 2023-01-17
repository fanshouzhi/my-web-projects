#### Javascript

- Vue ref方法定义基本响应式变量。如:

```js
const currentIndex = ref(0);
```

ref方法当然也可以定义一个对象，但是通常定义对象应该使用reactive方法。

- Vue v-for指令渲染列表。如:

```js
v-for="(item,index) in imageItems" 
```

v-for指令渲染时最好指定key属性，方便虚拟DOM Diff算法比对。

- Vue 动态绑定class与style。如:

```js
:class="index === currentIndex ? 'active' : ''"
:style="{ backgroundImage:`url(${ imageURL + item })`}"
```

`:class`和`:style`代表设置动态类名和动态行内样式，其中`:`为`v-bind`的简写，值可以是一个javascript表达式，如三元表达式，或者是对象，又或者是数组。

- Vue 事件绑定。如:

```js
@click="currentIndex = index"
```

vue事件可以简写为@ + 事件名，值为一个javascript表达式或者是一个函数。

#### less

- 定义公共样式

```less
.base-flex {
    display: flex;
    justify-content: center;
    align-items: center;
}
//使用方式
.app {
    .base-flex;
}
```

- 嵌套语法

```less
.app {
    //...这里写核心样式
    .ec-panel {
        //...这里写核心样式
    }
}
```

less定义变量是@ + 变量名，如:

```less
@width: 100px;
```

- &

该符号表示对父选择器的一个引用，例如:

```less
.ec-panel {
    //...核心样式
    &.active {
        //...核心样式
    }
}
```

其中&.active其实就是.ec-panel.active的写法。

