<template>
  <div class="home">
    <transition name="toast">
      <Toast v-if="showToast" />
    </transition>
    <Todos @badValue="triggerToast"/>
    <button @click="showToast = !showToast">Toggle Toast</button>
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
    const triggerToast = ()=> {
      showToast.value = true;
      setTimeout(()=>showToast.value = false, 2000)
    }
    return {
      showToast,
      triggerToast
    };
  },
};
</script>

<style>


.toast-enter-active {
  animation: wobble 0.6s ease;
}

.toast-leave-to {
  opacity: 0;
  transform: translateY(-60px);
}
.toast-leave-active {
  transition: all 0.3s ease;
}

@keyframes wobble {
  0% { transform: translateY(-100px); opacity: 0; }
  50% { transform: translateY(0px); opacity: 1; }
  60% { transform: translateX(8px); }
  70% { transform: translateX(-8px); }
  80% { transform: translateX(4px); }
  90% { transform: translateX(-4px); }
  100% { transform: translateX(0px); }
}
</style>