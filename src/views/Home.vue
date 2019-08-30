<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Scott's music blog" />
    <div v-html="sample" />
    <div class="main-deck">
      <b-card-group deck>
        <Card />
        <Card />
        <Card />
      </b-card-group>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Card from "@/components/Card.vue";

export default {
  name: "home",
  data() {
    return {
      sample: `<p>Some sample inline html for fun</p>`
    }
  },
  components: {
    HelloWorld,
    Card
  },

};
</script>

<style scoped>
/* .home {
  margin: 0% 5% 0% 5%;
  max-width: 800px;
} */
</style>

