#### Javascript

v-if与v-else指令，表示条件，v-html表示渲染html:

```html
<div class="rna-page-content">
    <slot>
        <template v-if="props.isRenderHTML">
            <p v-html="content"></p>
        </template>
        <template v-else>{{ props.content }}</template>
    </slot>
</div>
复制代码
```

#### typescript

typescript 定义接口通过interface关键字，就像定义对象一样，其后跟属性名:属性类型，如:

定义基本类型就是:类型值，如:

```ts
const URL: string = "";
//代表URL是一个字符串类型
复制代码
interface NavItemType {
    url:string;
    text:string;
    icon:string;
}
复制代码
```

typescript泛型，如:

```ts
Array<NavItemType>
复制代码
```

就代表是一个泛型，也就是数组类型，并且数组项的值应该是类型NavItemType，所以数据格式就应该类似如下:

```ts
export const navList = [
  {
    url: "http://www.eveningwater.com/",
    text: "个人网页",
    icon:"Website"
  },
  {
    url: "https://www.eveningwater.com/my-web-projects/",
    text: "我的项目",
    icon:"project"
  },
  {
    url: "http://github.com/eveningwater",
    text: "github",
    icon:"github"
  },
];
复制代码
```

再如:

```ts
Array<string> //表示定义一个字符串数组
复制代码
```

导出多个模块语法:

```ts
export { default as Content } from "./Content.vue";
export { default as Menu } from "./LeftMenu.vue";
export { default as NavList } from "./NavList.vue";
复制代码
```

表示将三个组件的默认模块更名为对应的名字。

#### less

:deep深度选择器，类似于vue2的>>>和/deep/,通常用于影响子组件的样式，也就是因为加了scoped组件只作用在当前组件，而无法作用到子组件，也就需要使用该选择器:

```less
:deep(p) {
    text-indent: 2em;
    color:@content_font_color;
    line-height: 2;
    margin-bottom: 15px;
    letter-spacing: 1px;
}
复制代码
```

动态样式访问数组变量，可以根据索引来访问，就像访问数组元素一样:

```less
background-image: v-bind("beforeResourceURL[0]");
复制代码
```

css同级元素选择器，如:

```less
& + .rna-nav-list ul {
    transform: translateX(15px);
    & .rna-nav-item {
       transform: translateX(0);
       transition-delay: .4s;
    }
}
复制代码
```

表示选中当前选择器的兄弟选择器.rna-nav-list。