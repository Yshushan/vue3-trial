<template>
  <div class="about">
    <h1>{{ msg }}</h1>
    <h2>{{ new Date().toLocaleString() }}</h2>
    <h2>{{ Math.max(1, 23, 4) }}</h2>
    <button @click="reverse">reverse</button>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const msg = ref("Vue3 trial");
    const reverse = () => {
      msg.value = msg.value
        .split("")
        .reverse()
        .join("");
    };
    return {
      msg,
      reverse
    };
  }
};
</script>
