<template>
  <section id="Blog-Api">
    <div id="app-vue">
      <div class="users">
        <div v-if="errored">
          <p>
            We're sorry, we're not able to retrieve this information at the
            moment, please try back later
          </p>
        </div>

        <div v-else>
          <h4 v-if="loading">Loading...</h4>
          <div v-for="post in posts" :key="post" class="post">
            {{ post.title }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
export default {
  name: "BlogApi",
  data() {
    return {
      posts: null,
      loading: false,
      errored: false,
    };
  },
  created() {
    axios
      .get(`http://jsonplaceholder.typicode.com/posts`)
      .then((response) => {
        // JSON responses are automatically parsed.
        this.posts = response.data;
      })
      .catch((error) => {
        console.log(error);
        this.errored = true;
      });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#app-vue {
  display: flex;
  justify-content: center;
  font-family: 'Karla', sans-serif;
  font-size: 20px;
}

.post {
  width: 300px;
  border: 1px solid black;
  display: flex;
  flex-direction: row;
  padding: 20px;
  background: #FFEEE4;
  margin: 10px;
}
</style>
