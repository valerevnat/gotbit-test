<template>
  <div class="tooltip" v-if="showTooltip" @click="hideToltip">
    <div class="tooltip-triangle"></div>
    <div class="tooltip-content">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts" setup>

  props: {
    showTooltip: {
      type: Boolean,
      default: false,
    },
  },
  
    const hideToltip = () => {
      emit("updateTooltip:showTooltip", false);
    };

</script>


<style lang="scss" scoped>
.tooltip {
  display: flex;
  align-items: center;

  &-content {
    width: 296px;
    height: 99px;
    background: #000000;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #ffffff;
    font-weight: 400;
    font-size: 14px;
    padding: 10px;
  }
  &-triangle {
    background: #000000;
    width: 20px;
    height: 20px;
    transform: rotate(45deg);
    position: relative;
    left: 3%;
  }
}
</style>


<!-- <template>
  <div class="tooltip" v-if="showTooltip" @click="hideToltip">
    <div class="tooltip-triangle"></div>
    <div class="tooltip-content">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "TooltipContainer",
  props: {
    showTooltip: {
      type: Boolean,
      default: false,
    },
  },
  setup(_, { emit }) {
    const hideToltip = () => {
      emit("updateTooltip:showTooltip", false);
    };

    return {
      hideToltip,
    };
  },
});
</script>


<style lang="scss" scoped>
.tooltip {
  display: flex;
  align-items: center;

  &-content {
    width: 296px;
    height: 99px;
    background: #000000;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #ffffff;
    font-weight: 400;
    font-size: 14px;
    padding: 10px;
  }
  &-triangle {
    background: #000000;
    width: 20px;
    height: 20px;
    transform: rotate(45deg);
    position: relative;
    left: 3%;
  }
}
</style>