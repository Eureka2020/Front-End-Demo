### 需求
- 默认列表第一项为红色，随后点击的项变为红色
### 实现思路
- 利用v-for渲染列表，并用item标记每一项和index标记对应索引；
- 利用v-bind动态绑定class，利用activeIndex记录被点击项的下标，默认是第一项；
- 利用@click绑定点击事件，传入的参数是被点击项的index值，用以改变被点击项的颜色。
### Demo展示
* [changeColor](https://eureka2020.github.io/Front-End-Demo/VueDemo/changeColor.html)<br>
### 代码实现
```Javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
      .active {
        color: red;
      }
    </style>
</head>
<body>

<div id="app">
  <ul>
    <li v-for="(item, index) in movies" :class="{'active': activeIndex === index}" @click="active(index)">{{ item }}</li>
  </ul>
</div>

<script src="vue.js"></script>

<script>
  const app = new Vue({
    el: '#app',
    data: {
      movies: ['星际穿越', '寻梦环游记', '怦然心动', '唐伯虎点秋香'],
      index: 0,
      activeIndex: 0
    },
    methods: {
      active(index) {
        this.activeIndex = index
      }
    }
  })
</script>

</body>
</html>
```
