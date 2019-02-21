<template>
  <div class="hello">
    <div class="msg" v-html="msg"></div>
    <div class="click" @click="doClick($event)">单击/双击我</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: `
      Vue同一元素同时设置click，dblclick事件时:<br>
        1. 若click事件不弹出对话框等之类的话，那么双击时，会先执行两次click，然后再执行dblclick事件；<br>
        2. 若click事件弹出一个对话框之类的浮层，那么只执行一次click事件且双击事件不会执行；解决办法就是记录点击次数，延迟执行点击事件。
      `,
      // 点击次数
      clickCount: 0
    }
  },
  methods: {
    //
    doClick (event) {
      // run click
      this.clickCount++
      if (this.clickCount === 1) {
        setTimeout(() => {
          if (this.clickCount === 1) {
            this.showA()
          } else {
            this.showB()
          }
          this.clickCount = 0
        }, 250)
      }
    },
    showA () {
      console.log('single click run')
      alert('单击弹框')
    },
    showB () {
      console.log('dblclick run')
      alert('双击弹框')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.click {
  background-color: aquamarine;
  width: 150px;
  margin: 0 auto;
  border: 1px solid #E7E7E7;
  border-radius: 20px;
  font-size: 14px;
  padding-top: 4px;
  padding-bottom: 4px;
}
.msg {
  text-align: left;
  font-size: 12px;
  margin-bottom: 20px;
}
</style>
