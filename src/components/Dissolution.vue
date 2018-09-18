<template>
  <div class="dissolution">
    <div class="model">
      <div :class="item === 1 ? 'block' : 'hidden'" v-for="(item, index) in items" :key="index"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dissolution',
  data () {
    return {
      items: new Array(100).fill(0),
      num: 40
    }
  },
  mounted () {
    this.dissolution()
  },
  methods: {
    dissolution () {
      const timer = setTimeout(() => {
        this.dissolution()
      }, 100)
      if (this.num <= 400) {
        this.randomNum(40)
        this.num = this.num + 40
      } else {
        clearTimeout(timer)
      }
    },
    randomNum (num) {
      let i = 0
      while (i < num) {
        const index = parseInt(Math.random() * 400)
        if (this.items[index] !== 1) {
          this.$set(this.items, index, 1)
          i++
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dissolution {
  width: 400px;
  height: 300px;
  background: #fff;
  text-align: center;
  color: #999;
  font-size: 20px;
  position: relative;
}
.dissolution .model {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  background: #000;
}
.block {
  width: 20px;
  height: 15px;
  float: left;
  background: #fff;
}
.hidden {
  width: 20px;
  height: 15px;
  float: left;
  background: #000;
}
</style>
