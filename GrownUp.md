## 一、框架使用遇到的问题

## 二、造轮子历险记（注意：自己在封装组件时要考虑后端【服务器】数据的对接是否容易，避免不必要的数据结构封装，【栗子：My-Slider组件的封装】）

1. 利用iview框架中的Tabs(标签页)组件，自己封装标签页

```js
//组件的封装
<!-- 自己封装的标签页组件 -->
<template>
  <Tabs>
    <TabPane v-for="item in tabsName"
             :label="item"
             :key="item">
      <slot :name="item"></slot>
    </TabPane>
  </Tabs>
</template>

<script>

export default {
  components: {},
  data() {
    return {

    };
  },
  props: {
    tabsName: {
      type: Array,
      default: []
    }
  },
  methods: {

  },
}
</script>
//组件的使用
<my-tabs :tabsName="tabsName">
          <div v-for="item in tabsName"
               :slot="item"
               :key="item">
            <div v-if="item === tabsName[0]">
              相应组件  
            </div>  
            <div v-else-if="item === tabsName[1]">
              相应组件  
            </div> 
            ...
          </div>
        </my-tabs>
```

![造轮子_标签页](D:\Desktop\software\Elena\进阶高级.assets\造轮子_标签页.png)
