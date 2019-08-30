<template>
  <b-card :title="post.title" :img-src="post.imgLink" img-alt="Image" img-top>
    <b-card-text>{{post.content}}</b-card-text>
    <b-button router-link :to="'/post/' + post.id" variant="primary">Go somewhere</b-button>
    <div slot="footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </b-card>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    post: Object
  }
};
</script>

<style scoped>
img {
  height: 40%;
}
</style>