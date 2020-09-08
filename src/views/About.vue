<template>
  <div class="about">
    <h1>{{ msg }}</h1>
    <button @click="reverse">reverse</button>
    <p><input type="text" v-model="text" /></p>
    <p>{{ textStats }}</p>
  </div>
</template>

<script>
import { ref, computed, watchEffect } from "vue";
export default {
  setup() {
    const msg = ref("Vue3 trial");
    const reverse = () => {
      msg.value = msg.value
        .split("")
        .reverse()
        .join("");
    };

    const text = ref("");
    const textStats = computed(() => {
      return `"${text.value}": ${text.value.length}`;
    });

    watchEffect(() => {
      console.log(textStats.value);
    });

    return {
      msg,
      reverse,
      textStats
    };
  }
};
</script>
