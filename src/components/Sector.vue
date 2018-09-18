<template>
  <div class="sector">
    <div class="model">
      <div class="left"></div>
      <div class="right"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dissolution',
  data () {
    return {
    }
  },
  mounted () {
    
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sector {
  position: relative;
  width: 400px;
  height: 300px;
}
.model {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  background: #000;
  overflow: hidden;
}
.left, .right {
  width: 50%;
  height: 100%;
  background: #fff;
}
.left {
  position: 
}
</style>
