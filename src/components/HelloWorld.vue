<template>
  <div class="home">
    <Toast v-if="showToast"/>
    <button @click="showToast = !showToast">Show Toast</button>
  </div>
</template>

<script>
import { ref } from 'vue';
import Toast from "./Toast.vue";
import Todos from "./Todos.vue";
export default {
  components:{Toast, Todos},
  setup() {
    const showToast = ref(false)
    return {
      showToast
    }
  }
}
</script>

<style>

</style>