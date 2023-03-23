<template>
  <v-card class="mx-auto" width="500" tile>
    <v-img :src="link" aspect-ratio="2"></v-img>

    <v-card-title v-html="title" />

    <v-card-actions>
      <v-btn @click="show = !show"> Show </v-btn>

      <v-spacer></v-spacer>

      <v-btn icon @click="show = !show">
        <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text v-html="text" />
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script>
export default {
  name: "ProjectCard",
  data: () => ({
    show: false,
  }),
  props: {
    title: {
      type: String,
      default: "",
    },
    text: {
      type: String,
      default: "",
    },
    link: {
      type: String,
      default: "",
    },
  },
};
</script>
