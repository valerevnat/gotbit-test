<template>
  <div class="modal-window" v-if="show" @click="hideModal">
    <div class="modal-content">
      <div class="modal-content-title">
        <slot name="title"></slot>
      </div>
      <div class="modal-content-subtitle">
        <slot name="subtitle"></slot>
      </div>
      <div class="modal-content-content">
        <slot name="content"></slot>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ModalWindow",
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  setup(props, { emit }) {
    const hideModal = () => {
      emit("update:show", false);
    };

    return {
      hideModal,
    };
  },
});
</script>

<style lang="scss" scoped>
.modal-window {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(2.5px);
  position: fixed;
  display: flex;

  .modal-content {
    margin: auto;
    background: #ffffff;
    border: 1px solid #f3f3f5;
    box-shadow: 0px 32px 64px rgba(36, 37, 38, 0.12);
    border-radius: 16px;
    min-width: 560px;
    min-height: 252px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 28px;
    &-title {
      font-weight: 700;
      font-size: 32px;
      color: #191a1b;
    }
    &-subtitle {
      font-weight: 400;
      font-size: 16px;
      color: #58595c;
    }
    &-content {
      margin-top: 32px;
    }
  }
}
</style>
