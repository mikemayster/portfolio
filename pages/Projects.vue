<template>
  <v-container>
    <div class="text-center mb-12 mt-5">
      <Title :title="title"></Title>
      <v-divider class="mt-5 mb-4 mx-auto" />
    </div>
    <v-row>
      <v-col cols="12" sm="12">
        <SectionChip
          :sections="sections"
          @searchSection="filterProjects"
        ></SectionChip>
      </v-col>
      <v-col v-for="(project, i) in projects" :key="i" cols="12" lg="6" md="6">
        <ProjectCard
          :title="project.title"
          :text="project.text"
          :link="project.link"
          :web="project.web"
          :key="i"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ProjectCard from "../components/projects/ProjectCard.vue";
import Title from "../components/Title.vue";
import SectionChip from "../components/projects/SectionChips.vue";
import { projects, globalSections } from "../components/projects/projects.json";

export default {
  name: "Projects",
  components: { ProjectCard, Title, SectionChip },
  data: () => ({
    projects: projects,
    title: "Projects",
    sections: globalSections,
  }),
  methods: {
    filterProjects: function (section) {
      this.projects = projects.filter((project) =>
        project.sections.includes(section)
      );
    },
  },
};
</script>
