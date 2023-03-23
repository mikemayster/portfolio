<template>
  <v-container>
    <v-row no-gutters>
      <v-col v-for="(skill, idx) in skills" :key="idx" lg="4" md="4" sm="4">
        <div class="item">
          <v-icon :color="skill.color" size="x-large">{{ skill.img }}</v-icon>
          <span class="caption">{{ skill.name }}</span>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "SkillList",
  props: ["skills"],
};
</script>
<style>
div.item {
  text-align: center;
}
img {
  display: block;
  margin: 0 auto;
}
.caption {
  display: block;
}
</style>
