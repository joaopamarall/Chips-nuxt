<template>
  <div class="chips">
    <div v-for="(gender, index) in genderOptions" :key="index">
      <Chips :gender="gender" :active="gender === selectedGender" @click.native="selectGender(gender)" />
    </div>
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
      genderOptions: ["Mulheres", "Homens", "Trans"],
      selectedGender: "Mulheres",
    };
  },
  methods: {
    selectGender(gender) {
      this.selectedGender = gender;
      const newRoute = `/gender/${gender.toLowerCase()}`;
      window.location.pathname = newRoute;
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
