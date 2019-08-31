<template>
  <div v-if="isLoading == false">
    <img class="picture" :src="post.imgLink" />
    <h1>{{post.title}}</h1>
    <p>{{post.content}}</p>
    <p v-if="error">{{error}}</p>
  </div>
</template>

<script>
import Posts from "@/json/Posts.json";

export default {
  name: "post",
  data() {
    return {
      posts: Posts,
      loading: false,
      post: {},
      error: "",
      isLoading: false
    }
  },
  created() {
    // fetch the data when the view is created and the data is
    // already being observed
    this.fetchData()
  },
  watch: {
    // call again the method if the route changes
    '$route': 'fetchData'
  },
  methods: {
    getPost() {
      Object.values(this.posts).map((post) => {
        if (post.id == this.$route.params.id) {
          this.post = post
        } else if (this.post == {}) {
          this.err = "Not Found"
        }
      })
    },
    fetchData() {
      this.error = this.post = null
      this.loading = true
      // replace `getPost` with your data fetching util / API wrapper
      this.getPost(this.$route.params.id)
      this.loading = false
    }
  }
}
</script>

<style scoped>
.picture {
  max-width: 100%;
  padding-top: 5%;
}
</style>