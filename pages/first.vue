<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">invoke_brl_twice</h1>
      <h2 class="subtitle">top page</h2>
      <div class="links">
        <nuxt-link to="/first" class="button--green">goto top</nuxt-link>
        <nuxt-link to="/second" class="button--green">goto second</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Logo from "~/components/Logo.vue";
import { Component } from "nuxt-property-decorator";

@Component({
  components: { Logo }
})
export default class OnePage extends Vue {
  beforeRouteEnter(to, from, next) {
    if (from.name === "second") {
      next("/");
    } else {
      next();
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
