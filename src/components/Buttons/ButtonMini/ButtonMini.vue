<template>
  <div>
    <button class="btn-mini">
      <slot></slot>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "ButtonMini",
});
</script>

<style lang="scss" scoped>
@import "../../../assets/variables.scss";

.btn-mini {
  width: 157px;
  height: 44px;
  border: 2px solid $main-color;
  border-radius: 8px;
  background-color: inherit;
  cursor: pointer;
}
</style>