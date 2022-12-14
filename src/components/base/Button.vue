<template>
  <div>
    <button :class="btnClass">
      <slot></slot>
    </button>
  </div>
</template>



<script lang="ts" setup>
import { ref } from "vue";

const btnClass = ref("tn-main");
</script>

<style lang="scss" scoped>
@import "../../../assets/variables.scss";
.btn-main {
  width: 312px;
  height: 52px;
  color: #ffffff;
  font-size: 16px;
  border: none;
  background: $main-color;
  border-radius: 8px;
  cursor: pointer;
}

.btn-mini {
  width: 157px;
  height: 44px;
  border: 2px solid $main-color;
  border-radius: 8px;
  background-color: inherit;
  cursor: pointer;
}
</style>