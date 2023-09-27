<template>
  <div class="chip" :class="{ 'active': isActive }" @click="handleClick">
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
  methods: {
    handleClick() {
      this.$emit('click', this.gender);
    },
  },
};
</script>

<style>
.chip {
  background-color: rgb(206, 230, 241);
  color: rgb(90, 136, 121);
  border: 2px solid rgb(90, 136, 121);
  border-radius: 40px;
  padding: 8px;
  cursor: pointer;
}

.chip.active {
  background-color: rgba(93, 122, 137, 1);
  color: #fff;
}
</style>
