<template>
  <div class="text-center">
    <v-chip
      class="ma-2"
      color="info--text"
      variant="outlined"
      @click="searchSection(section.title)"
      v-for="(section, i) in sections"
      :key="i"
    >
      <v-avatar left>
        <v-icon>{{ section.icon }}</v-icon>
      </v-avatar>
      {{ section.title }}
    </v-chip>
  </div>
</template>
<script>
export default {
  name: "SectionChips",
  props: ["sections"],
  methods: {
    searchSection: function (title) {
      this.$emit("searchSection", title);
    },
  },
};
</script>
