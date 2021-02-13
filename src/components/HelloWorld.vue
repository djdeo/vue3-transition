<template>
  <div class="home">
    <transition name="toast">
      <Toast v-if="showToast" />
    </transition>
    <button @click="showToast = !showToast">Show Toast</button>
  </div>
</template>

<script>
import { ref } from "vue";
import Toast from "./Toast.vue";
import Todos from "./Todos.vue";
export default {
  components: { Toast, Todos },
  setup() {
    const showToast = ref(false);
    return {
      showToast,
    };
  },
};
</script>

<style>

/* toast enter */
.toast-enter-from {
  opacity: 0;
  transform: translateY(-60px);
}
.toast-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.toast-enter-active {
  transition: all 0.3s ease;
}
.toast-leave-from {
  opacity: 1;
  transition: translateY(0);
}

.toast-leave-to {
  opacity: 0;
  transform: translateY(-60px);
}
.toast-leave-active {
  transition: all 0.3s ease;
}
</style>