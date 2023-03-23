<template>
  <v-container class="wrapper">
    <h1 class="glitch" :text-render="textRender">{{ textRender }}</h1>
  </v-container>
</template>

<script>
export default {
  name: "Title",
  props: ["title"],
  data() {
    return {
      textRender: this.title,
    };
  },
};
</script>

<style scoped lang="scss">
.wrapper {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  h1.glitch {
    // font-family: sans-serif;
    font-weight: 800;
    position: relative;
    font-size: 70px;
  }
  h1.glitch::before,
  h1.glitch::after {
    color: white;
    content: "" attr(text-render) "";
    position: absolute;
    width: 100%;
    height: 100%;
    background: var(--v-background-base, black) !important;
    overflow: hidden;
    top: 0;
  }
  h1.glitch::before {
    left: 3px;
    text-shadow: -2px 0 var(--v-error-base, red);
    animation-name: glitch-animation-1;
    animation-duration: 2s;
    animation-timing-function: linear;
    animation-delay: 0s;
    animation-iteration-count: infinite;
    animation-direction: reverse-alternate;
  }
  h1.glitch::after {
    left: -3px;
    text-shadow: -2px 0 var(--v-info-base, blue);
    animation-name: glitch-animation-2;
    animation-duration: 2s;
    animation-timing-function: linear;
    animation-delay: 0s;
    animation-iteration-count: infinite;
    animation-direction: reverse-alternate;
  }
}
@keyframes glitch-animation-1 {
  $steps: 20;
  @for $i from 0 through $steps {
    #{percentage($i*(1/$steps))} {
      clip: rect(random(300) + px, 500px, random(150) + px, 10px);
    }
  }
}
@keyframes glitch-animation-2 {
  $steps: 20;
  @for $i from 0 through $steps {
    #{percentage($i*(1/$steps))} {
      clip: rect(random(300) + px, 500px, random(150) + px, 10px);
    }
  }
}
</style>
