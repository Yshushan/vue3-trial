<template>
  <div class="about">
    <h1>{{ msg }}</h1>
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
