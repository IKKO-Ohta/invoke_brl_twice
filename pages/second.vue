<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">double_invoke_beforeRouteEnter</h1>
      <h2 class="subtitle">second page</h2>
      <div class="links">
        <button @click="backToBack" class="button--green">back-to-back</button>
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
export default class SecondPage extends Vue {
  backToBack() {
    this.$router.push({ path: "/one" });
  }

  beforeRouteLeave(to, from, next) {
    console.log("hoge????");
    next();
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
