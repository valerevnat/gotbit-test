<template>
  <div class="container">
    <MainScreen>
      <BasicContent
        :handlerShowModal="handlerShowModal"
        :handlerContentModal="handlerContentModal"
      />
      <ModalWindow v-model:show="hideWindow">
        <template v-slot:title> Title metamask </template>
        <template v-slot:subtitle> Subtitle metamask </template>
        <template v-slot:content> Slot for metamask </template>
        <!-- <div v-if="contentModal === 'metamask'">Контент с метамаском</div> -->
      </ModalWindow>
    </MainScreen>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import MainScreen from "../MainScreen/MainScreen.vue";
import BasicContent from "../BasicContent/BasicContent.vue";
import ModalWindow from "../ModalWindow/ModalWindow.vue";

export default defineComponent({
  name: "ContainerComponent",
  components: {
    MainScreen,
    BasicContent,
    ModalWindow,
  },

  setup() {
    const hideWindow = ref<boolean>(false);
    const contentModal = ref<string>("");

    const handlerShowModal = () => {
      hideWindow.value = !hideWindow.value;
    };

    const handlerContentModal = (payload: string) => {
      contentModal.value = payload;
    };

    return {
      hideWindow,
      contentModal,
      handlerShowModal,
      handlerContentModal,
    };
  },
});
</script>


<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 44px;
}
</style>