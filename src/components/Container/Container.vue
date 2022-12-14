<template>
  <div class="container">
    <MainScreen>
      <BasicContent
        :handlerShowModal="handlerShowModal"
        :handlerContentModal="handlerContentModal"
      />
      <ModalWindow v-model:show="hideWindow">
        <template v-if="contentModal === 'basic'">
          <div class="title-modal">Connect wallet</div>
          <div class="subtitle-modal">
            To perform actions on this page you need to connect your wallet
          </div>
          <div class="modal-content-main">
            <ButtonMini @click="conectMetaMask">
              <div class="modal-content-main-btn">
                <img src="../../resorces/img/logo-mask.png" alt="MetaMask" />
                <div>MetaMask</div>
              </div>
            </ButtonMini>
          </div>
        </template>
      </ModalWindow>
    </MainScreen>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import MainScreen from "../MainScreen/MainScreen.vue";
import BasicContent from "../BasicContent/BasicContent.vue";
import ModalWindow from "../ModalWindow/ModalWindow.vue";
import ButtonMini from "../Buttons/ButtonMini/ButtonMini.vue";

export default defineComponent({
  name: "ContainerComponent",
  components: {
    MainScreen,
    BasicContent,
    ModalWindow,
    ButtonMini,
  },

  setup() {
    const hideWindow = ref<boolean>(false);
    const contentModal = ref<string>("");

    const handlerShowModal = () => {
      hideWindow.value = !hideWindow.value;
    };

    const handlerContentModal = (payload: string) => {
      contentModal.value = payload;
      console.log("payload", payload);
    };

    const conectMetaMask = () => {
      console.log("Conect MetaMask");
    };

    return {
      hideWindow,
      contentModal,
      handlerShowModal,
      handlerContentModal,
      conectMetaMask,
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

  .modal-content-main {
    margin-top: 32px;
    width: 100%;
    &-btn {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-weight: 500;
      font-size: 20px;
      color: #191a1b;
    }
    .btn-mini {
      width: 100%;
      height: 72px;
    }
  }
}
</style>