<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <HelloWorld msg="Scott's music blog" />
    <div v-html="sample" />
    <div class="main-deck">
      <b-card-group deck>
        <Card :key="post.title" v-for="post in postData" :post="post" />
      </b-card-group>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Card from "@/components/Card.vue";
import Posts from "@/json/Posts.json";

export default {
  name: "home",
  data() {
    return {
      sample: `<p>Sample for vue practice</p>`,
      postData: Posts
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

