<template>
  <v-card width="800">
    <v-img height="200px" :src="career.image">
      <v-card-title>{{ career.title }}</v-card-title>
    </v-img>

    <v-card-text>
      <div class="font-weight-bold ml-8 mb-2">
        {{ career.timeline }}
      </div>

      <v-timeline align-top dense>
        <v-timeline-item
          v-for="message in messages"
          :key="message.time"
          :color="message.color"
          small
        >
          <div>
            <div class="font-weight-normal">
              <strong>{{ message.time }}</strong>
            </div>
            <div class="font-weight-normal">
              <strong>{{ message.company }}</strong>
            </div>
            <div>{{ message.message }}</div>
            <div class="mt-2 info--text">{{ message.tags }}</div>
          </div>
        </v-timeline-item>
      </v-timeline>
    </v-card-text>
  </v-card>
</template>
<script>
import { messages, career } from "./career.json";

export default {
  name: "CareerCard",
  data: () => ({
    messages: messages,
    career: career,
  }),
};
</script>
