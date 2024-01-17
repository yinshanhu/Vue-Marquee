# 无缝滚动插件,可触摸

## 例子：

* template
 ```
<Marquee :list="listData" :step="listData.length < 5 ? 0 : 0.6">
    <div class="list-item" @click="toDetail(j)" v-for="(j, idx) in listData" :key="'subc_' + idx">
        <img :src="j.productImg" alt="" />
        <div class="info">
            <p class="p1">{{ j.mainTitle }}</p>
            <p class="p2">{{ j.subTitle }}</p>
        </div>
    </div>
</Marquee>
 ```

* script

```
import Marquee from "Marquee.vue";
```

```
export default {
  data(){
    return {
      listData: [{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机",
		productImg: "https://xx.xx.com/100030.jpg",
      },{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机1",
		productImg: "https://xx.xx.com/100030.jpg",
      },{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机2",
		productImg: "https://xx.xx.com/100030.jpg",
      },{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机3",
		productImg: "https://xx.xx.com/100030.jpg",
      },{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机4",
		productImg: "https://xx.xx.com/100030.jpg",
      },{
		mainTitle: "iphone",
		subTitle: "宇宙最强手机5",
		productImg: "https://xx.xx.com/100030.jpg",
      }]
    }
  }
}
```
 
* style

```
.seamless-list-container {
    display: flex;
    .list-item {
        position: relative;
        width: 1.22rem;
        height: 1.56rem;
        margin-right: 0.13rem;
        flex-shrink: 0;

        .info {
            position: absolute;
            bottom: 0.08rem;
            color: #600019;
            width: 100%;
            text-align: center;

            .p1 {
                font-size: 0.22rem;
                white-space: nowrap;
                overflow: hidden;
                text-overflow: ellipsis;
                font-weight: bold;
                margin-top: 0.02rem;
            }

            .p2 {
                font-size: 0.18rem;
                white-space: nowrap;
                overflow: hidden;
                text-overflow: ellipsis;
            }
        }
    }
}
```

## API

> **props**
>---
>| 参数 | 说明 | 类型 | 默认值 |
>|-----|:------|------|-------|
>| list | 用来渲染滚动的列表，必传，数组内数据格式不固定，一般是字符串数组，但如果没有插槽的话显示的内容可能会和你想象的不一样 | Array | - |
>| step | 滚动速度，绝对值越大越快，可以为负数 | Number | 1 | 
>| unlimited | 是否是无限滚动模式，朝一个方向无限滚动，不会再回到列表开头，需要动态向list中添加数据 | Boolean | false | 
>| direction | 方向，horizontal: 水平, vertical: 垂直 | String | horizontal | 
>| touchMove | 是否跟随手指触摸移动 | Boolean | true | 

> **event**
>---
>| 事件名 | 说明 | 回调参数 |
>|-----|:------|-------|
>| changePosition | 当列表滚动时触发 |  { position: 滚动位置 ,height: 容器高度,width: 容器宽度,innerHeight: 列表高度,innerWidth: 列表宽度}  |


