<template>
  <div style=" position: relative;">
    <div id="fortest">

      {{ positionX }}
      {{ positionY }}
      {{ value }}
      <el-button type="primary">llll</el-button>

    </div>

    <div class="esli">
      <el-slider
        v-model="value"
        vertical
        height="500px"
      />

    </div>
  </div>
</template>

<script>
export default {
  components: {

  },
  data() {
    return {
      positionX: 0,
      positionY: 0,
      value: 0
    }
  }, methods: {
    move(e) {
      const odiv = e.target // 获取目标元素

      // 算出鼠标相对元素的位置
      const disX = e.clientX - odiv.offsetLeft
      const disY = e.clientY - odiv.offsetTop
      document.onmousemove = (e) => { // 鼠标按下并移动的事件
        // 用鼠标的位置减去鼠标相对元素的位置，得到元素的位置
        const left = e.clientX - disX
        const top = e.clientY - disY

        // 绑定元素位置到positionX和positionY上面
        this.positionX = top
        this.positionY = left

        // 移动当前元素
        // odiv.style.left = left + 'px'
        odiv.style.top = top + 'px'
      }
      document.onmouseup = (e) => {
        document.onmousemove = null
        document.onmouseup = null
      }
    }

  }
}
</script>

<style lang="scss">
#fortest {
  position: relative;     /*定位*/
  top: 10px;
  left: 10px;
  width: 200px;
  height: 200px;
  background: #666;       /*设置一下背景*/
}

.esli {
  position: absolute;

}
</style>
