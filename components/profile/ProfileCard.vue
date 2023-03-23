<template>
  <v-card class="mx-auto" width="800" tile>
    <v-list-item three-line>
      <v-row class="my-2">
        <v-col cols="12" lg="4" md="4" sm="12" class="d-none d-md-block">
          <v-avatar size="150">
            <img alt="user" :src="greetings.avatar" />
          </v-avatar>
        </v-col>
        <v-col cols="12" lg="8" md="8" sm="12">
          <v-list-item-content>
            <div class="text-overline mb-4 info--text">
              {{ greetings.greeting }}
            </div>
            <v-list-item-title class="text-h5 mb-1">
              <h1 class="typewriter" v-text="greetings.title" />
            </v-list-item-title>
            <v-list-item-subtitle>
              <h1 v-text="greetings.subTitle" />
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-col>
      </v-row>
    </v-list-item>

    <v-card-text>
      <div class="my-4 text-subtitle-1">
        <p v-html="greetings.caption" />
        <v-btn
          href="./resume/resume.pdf"
          target="_blank"
          v-if="greetings.resumeEnabled"
        >
          Resume!
        </v-btn>
      </div>
      <v-divider class="mt-5 mb-4 mx-auto" />
      <v-row class="justify-end">
        <v-btn
          v-for="(contact, i) in greetings.contacts"
          :key="i"
          :href="contact.src"
          target="_blank"
          icon
        >
          <v-icon>{{ contact.icon }}</v-icon>
        </v-btn>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
import Greetings from "./greetings.json";
export default {
  name: "ProfileCard",
  data() {
    return {
      greetings: Greetings,
    };
  },
};
</script>

<style scoped>
.typewriter {
  overflow: hidden;
  white-space: nowrap;
  width: 0;
  animation: typing 3s steps(30, end) forwards;
}

@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}
</style>
