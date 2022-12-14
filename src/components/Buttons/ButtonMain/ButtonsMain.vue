<template>
  <div>
    <button class="btn-modal">
      <slot></slot>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ButtonsMain",
  setup() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
@import "../../../assets/variables.scss";
.btn-modal {
  width: 312px;
  height: 52px;
  color: #ffffff;
  font-size: 16px;
  border: none;
  background: $main-color;
  border-radius: 8px;
  cursor: pointer;
}
</style>