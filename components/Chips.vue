<template>
  <div class="chip" :class="{ 'is-active': isActive }">
    {{ label }}
  </div>
</template>

<script>
export default {
  name: 'Chips',
  props: {
    label: String,
    isActive: Boolean,
  },
  computed: {
    labelClasses() {
      return {
        chip: true,
        isActive: this.isActive,
      };
    },
  },
};
</script>

<style lang="scss" >
.chip {
    background-color: marrom;
    color: branco;
    border: solid 2px marrom;
    border-radius: 40px;
    padding: 8px;
    cursor: pointer;

    &.is-active {
      background-color: marrom;
      color: preto;
    }
  }
</style>
