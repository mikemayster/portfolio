<template>
  <v-card width="800">
    <v-row class="my-2">
      <v-col cols="12" lg="6" md="6" sm="12">
        <div>
          <div class="burger-overlay">
            <div
              @mouseover="hoverBurger(frontEnd)"
              @mouseleave="hoverBurger(defaultSkills)"
              class="top-overlay"
            ></div>
            <div
              @mouseover="hoverBurger(tools)"
              @mouseleave="hoverBurger(defaultSkills)"
              class="mid-overlay"
            ></div>
            <div
              @mouseover="hoverBurger(backEnd)"
              @mouseleave="hoverBurger(defaultSkills)"
              class="bot-overlay"
            ></div>
          </div>

          <img :src="burger" style="max-width: 60%; width: 100%" />
        </div>
      </v-col>
      <v-col cols="12" lg="6" md="6" sm="6">
        <v-card-text>
          <div v-if="activeLayer.title === 'None'">
            <p class="text-shadow info--text">
              <small>
                Hover the Burger layers to know something more about my tech
                skills
              </small>
            </p>
          </div>

          <div v-if="activeLayer.title === 'Front End'">
            <h3 class="align-center">Front End</h3>
            <SkillList :skills="frontEnd.stacks" />
          </div>

          <div v-if="activeLayer.title === 'Back End'">
            <h3 class="align-center">Back End</h3>
            <SkillList :skills="backEnd.stacks" />
          </div>

          <div v-if="activeLayer.title === 'Tools'">
            <h3 class="align-center">Tools</h3>
            <SkillList :skills="tools.stacks" />
          </div>
        </v-card-text>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
import SkillList from "./SkillList.vue";
import skills from "./skills.json";

export default {
  name: "SkillsCard",
  components: { SkillList },
  data() {
    return {
      defaultSkills: skills.defaultSkills,
      activeLayer: skills.frontEnd,
      burger: skills.frontEnd.burger,
      frontEnd: skills.frontEnd,
      backEnd: skills.backEnd,
      tools: skills.tools,
      burgerInterval: skills.burgerInterval,
    };
  },
  methods: {
    hoverBurger: function (layer) {
      this.burger = layer.burger;
      this.activeLayer = layer;
    },
    handleBurgerInterval(_me) {
      const title = _me.activeLayer.title;
      if (title === "None") {
        _me.hoverBurger(_me.frontEnd);
      }
      if (title === "Front End") {
        _me.hoverBurger(_me.tools);
      }
      if (title === "Tools") {
        _me.hoverBurger(_me.backEnd);
      }
      if (title === "Back End") {
        _me.hoverBurger(skills.defaultSkills);
      }
    },
  },
  mounted() {
    const _me = this;
    setInterval(function () {
      _me.handleBurgerInterval(_me);
    }, _me.burgerInterval);
  },
};
</script>

<style lang="scss">
.burger-overlay {
  position: absolute;
  top: 0;
  height: 316px;
  width: 350px;
  cursor: pointer;
  z-index: 3;

  .top-overlay {
    z-index: 6;
    width: 100%;
    height: 30%;
  }
  .mid-overlay {
    z-index: 6;
    width: 100%;
    height: 25%;
  }
  .bot-overlay {
    z-index: 6;
    width: 100%;
    height: 20%;
  }
}

.align-center {
  text-align: center;
  vertical-align: center;
}

.text-shadow {
  font-style: italic;
  text-transform: uppercase;
  color: transparent;
  -webkit-text-stroke-width: 1px;
  text-shadow: 2px 2px 10px #2962ff;
  transition: all 0.5s ease-in-out;
  text-align: center;
  letter-spacing: 0.2em;
  animation: flicker 0.5s ease-in-out infinite alternate;
}

@keyframes flicker {
  0% {
    opacity: 0.5;
    text-shadow: 2px 2px 10px #2962ff;
  }
  100% {
    opacity: 1;
    text-shadow: 2px 2px 20px #2962ff;
  }
}
</style>
