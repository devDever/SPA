<template>
  <div id="app">
    <navbar />
    <b-container>
      <router-view />
    </b-container>
  </div>
</template>

<script>
import navbar from "@/components/NavBar";
export default {
  components: {
    navbar,
  },
};
</script>

<style lang="scss"></style>
