<template>
  <div class="MoreDetails">
      <div class="card" v-if="commit.commit">
          <p>{{ ID }}</p>
          <p>{{ commit.commit.author.name }}</p>
          <p>{{ commit.commit.author.email }}</p>
          <p>{{ commit.commit.author.date }}</p>
          <p>{{ commit.commit.message }}</p>
      </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "MoreDetails",
  data() {
    return {
      ID: this.$route.params.ID,
      commit: [],
    };
  },

  async mounted() {
    const get = await axios.get(
      `https://api.github.com/repos/vuejs/vue/commits/${this.ID}`
    );
    this.commit = get.data;
    console.log(this.commit);
  },
};
</script>

<style></style>
