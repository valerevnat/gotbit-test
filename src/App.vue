<template>
  <Navigation />
  <ContainerComponent />
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Navigation from "./components/Navigation/Navigation.vue";
import ContainerComponent from "./components/Container/Container.vue";
// import ModalWindow from "./components/ModalWindow/ModalWindow.vue";

export default defineComponent({
  name: "App",
  components: {
    Navigation,
    ContainerComponent,
    // ModalWindow,
  },

  // setup() {
  //   const hideWindow = ref<boolean>(false);

  //   const handlerShowModal = () => {
  //     hideWindow.value = !hideWindow.value;
  //   };

  //   return {
  //     hideWindow,
  //     handlerShowModal,
  //   };
  // },
});
</script>

<style>
</style>
