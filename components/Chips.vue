<template>
  <div class="chip" :class="{labelClasses}">
    {{ gender }}
  </div>
</template>

<script>
export default {
  name: 'Chips',
  props: {
    gender: String,
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

<style >
.chip {
  background-color: rgb(206, 230, 241);
  color: rgb(90, 136, 121);
  border: 2px solid rgb(90, 136, 121);
  border-radius: 40px;
  padding: 8px;
  cursor: pointer;
}

.chip.isActive {
  background-color: rgba(93, 122, 137, 1);
  color: #fff;
}
</style>
