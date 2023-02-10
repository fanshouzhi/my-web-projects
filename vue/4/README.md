### Javascript

给元素或者是组件绑定ref，可以访问组件或者元素的实际DOM元素，例如:

``` ts
   const inputRef = ref(null);
```

watch方法，接受三个参数，第一个参数表示监听的数据，可以是一个函数，也可以是一个变量，或者也可以是一个监听的字符串属性名，第二个参数则是一个回调函数，可以获取到监听的值，第三个参数表示监听的配置对象，如深度监听deep属性。如:


``` ts
watch(isActive,val => {
    const inputElement = inputRef.value;
    if(val && inputElement){
        (inputElement as HTMLInputElement).focus();
    }
});
```

### typescript

as 关键字可以将任意变量断言成任意类型，通常如果转换类型不对可以先强制转换成unknown，然后再转换成对应的类型。例如:

``` ts
 //假设inputElement不能被断言成HTMLInputElement类型，就需要先转换成unknown
inputElement as unknown as HTMLInputElement
```

或者也可以直接断言成any。如:

```ts 
inputElement as any 
```
虽然这样做可以逃避ts的类型检查，但如无必要，尽量少使用as关键字断言变量的类型。

模板绑定

``` html
<input type="text" class="hsw-input" ref="inputRef" :placeholder="props.placeHolder" />
```

其它知识点同前面示例。