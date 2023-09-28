<template>
  <div class="chips">
    <Chips 
      v-for="(gender, index) in gender"
      :key="index"
      :gender="gender"
      :active= "gender === selectedGender"
      @click.native="selectgender(gender)"
    />
  </div>
</template>

<script>
import Chips from '@/components/Chips.vue';

export default {
  name: "indexPage",
  components: {
    Chips,
  },
  data() {
    return {
      gender: ["Mulheres", "Homens", "Trans"],
      selectedGender: "Mulheres",
      isActive: false
    };
  },
  methods: {
    selectgender(gender) {
      this.selectedGender = gender;
      const newRoute = `/${gender.toLowerCase()}`;
      window.history.replaceState(null, null, newRoute);
    },
  },
};
</script>

<style>
body {
  background-color: rgb(206, 230, 241);
}

.chips {
  display: flex;
  justify-content: center;
  gap: 20px;
}
</style>
