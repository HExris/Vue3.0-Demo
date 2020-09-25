<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    <div class="footer">
      <span>Powerd by</span>
      <img alt="Vue logo" src="../assets/logo.png" /> with <i>❤️</i>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Options({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {}
</script>
<style lang="less" scoped>
.footer {
  display: flex;
  align-items: center;
  justify-content: center;
  vertical-align: middle;
  font-family: "Mircosoft Yahei";
  img,
  i {
    margin: 0 8px;
  }
  img {
    width: 20px;
  }
  i {
    font-size: 20px;
    font-style: normal;
  }
}
</style>
