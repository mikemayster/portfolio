<template>
  <v-app dark>
    <!-- <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" fixed app>
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <template v-if="item.isEnabled">
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </template>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>

      <v-btn icon @click="$vuetify.theme.dark = !$vuetify.theme.dark">
        <v-icon>mdi-invert-colors</v-icon>
      </v-btn>

      <v-toolbar-title>{{ title }}</v-toolbar-title>

      <v-spacer />
      <v-btn href="https://github.com/mikemayster" target="_blank" icon>
        <v-icon>mdi-github</v-icon>
      </v-btn>
    </v-app-bar> -->

    <v-app-bar app fixed>
      <v-toolbar-items>
        <v-btn @click="$vuetify.theme.dark = !$vuetify.theme.dark" icon>
          <v-icon>mdi-invert-colors</v-icon>
        </v-btn>
      </v-toolbar-items>

      <v-spacer />

      <div class="d-none d-lg-block">
        <v-btn
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          class="mr-10"
          text
          v-if="item.isEnabled"
        >
          {{ item.title }}
        </v-btn>
      </div>

      <v-toolbar class="d-lg-none" collapse flat color="transparent">
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-card-actions class="justify-center">
              <v-btn icon v-on="on">
                <v-icon>mdi-menu</v-icon>
              </v-btn>
            </v-card-actions>
          </template>

          <v-list>
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
              :to="item.to"
              router
              exact
              v-if="item.isEnabled"
            >
              <template>
                <v-list-item-action>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item-content>
              </template>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import { routes, wallet } from "../router/route.json";
import Footer from "./footer.vue";

export default {
  name: "DefaultLayout",
  components: { Footer },
  data() {
    return {
      drawer: false,
      items: routes,
      miniVariant: false,
      title: wallet.title,
    };
  },
};
</script>
