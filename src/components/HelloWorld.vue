<template>
  <div class="hello">
    <p>String operation Testing</p>
    <div class="test-block">
      <h2 @click="toggleWelcomeMsg">{{ state.msg }}</h2>
    </div>
    <p>Number operation Testing</p>
    <div class="test-block">
      <h2 @click="increment">
        {{ `Current Count : ${state.count} * 2 = ${state.double}` }}
      </h2>
    </div>
    <p>Render Testing</p>
    <div class="test-block">
      <div class="block-title">Loop</div>
      <ol class="text">
        <li v-for="(item, index) in state.personList" :key="index">
          {{ `My Name is ${item.name} and ${item.age} years old.` }}
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
import { reactive, computed } from "vue";

export default {
  setup() {
    const state = reactive({
      count: 0,
      msg: "Hello world",
      double: computed(() => state.count * 2),
      personList: [
        {
          name: "Tom",
          age: 20
        },
        {
          name: "Exris",
          age: 20
        },
        {
          name: "Franky",
          age: 20
        },
        {
          name: "Gracie",
          age: 20
        },
        {
          name: "Lee",
          age: 20
        }
      ]
    });

    function increment() {
      state.count++;
    }

    function toggleWelcomeMsg() {
      state.msg =
        state.msg === "Hello world"
          ? "Welcome Vue.js 3.0 RFC test !"
          : "Hello world";
    }

    return {
      state,
      increment,
      toggleWelcomeMsg
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
p {
  font-size: 30px;
  color: #333;
  text-align: left;
  padding-left: 40px;
}
h2 {
  user-select: none;
  cursor: pointer;
}
.test-block {
  background-color: #dcdcdc;
  color: #fff;
  padding: 20px;
  margin: 40px;
  border-radius: 15px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.18);
  ul,
  ol {
    padding-left: 20px;
    li {
      line-height: 30px;
    }
  }
  .block-title {
    text-align: left;
    color: #555;
    font-size: 20px;
  }
  .text {
    color: #666;
    font-size: 15px;
    margin: 10px 0;
    text-align: left;
  }
}
</style>
