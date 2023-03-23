<template>
  <v-container>
    <v-row class="py-2" justify="space-around">
      <ProfileCard />
    </v-row>
    <v-row class="py-2" justify="space-around">
      <SkillsCard />
    </v-row>
    <v-row class="py-2" justify="space-around">
      <CareerCard />
    </v-row>
  </v-container>
</template>

<script>
import CareerCard from "../components/career/CareerCard.vue";
import ProfileCard from "../components/profile/ProfileCard.vue";
import SkillsCard from "../components/skills/SkillsCard.vue";

export default {
  name: "Welcome",
  components: { CareerCard, ProfileCard, SkillsCard },
};
</script>
