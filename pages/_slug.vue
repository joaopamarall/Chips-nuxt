<template>
  <div>
    <div>
      <router-link to="/">Ir para home</router-link>
    </div>
    <div class="chips">
      <Chips
        v-for="(gender, index) in genderOptions"
        :key="index"
        :label="gender"
        :isActive="isGenderActive(gender)"
        @click.native="selectGender(gender)"
      />
    </div>
  </div>
</template>

<script>
import Chips from "@/components/Chips.vue";

export default {
  name: "indexPage",
  components: {
    Chips,
  },
  data() {
    return {
      genderOptions: ["Mulheres", "Homens", "Crianças"],
      selectedGender: "Mulheres",
    };
  },
  mounted() {
    this.setSelectedGenderFromRoute();
  },
  methods: {
    setSelectedGenderFromRoute() {
      this.selectedGender = this.$route.params.slug || "Mulheres";
    },
    isGenderActive(gender) {
      return gender.toLowerCase() === this.selectedGender.toLowerCase();
    },
    selectGender(gender) {
      this.selectedGender = gender;
      const newRoute = `/${gender.toLowerCase()}`;
      window.history.replaceState(null, null, newRoute);
    },
  },
};
</script>

<style lang="scss">
body {
  background-color: bege;
}

.chips {
  display: flex;
  justify-content: center;
  gap: 20px;
}
</style>
