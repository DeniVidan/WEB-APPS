<template>
  <div class="home">

    <data-info v-for="commit in commit" :id="commit.sha" :details="commit.commit.message" :key="commit.sha"/>

  </div>
</template>

<script>

import axios from "axios";
import dataInfo from "@/components/dataInfo.vue"


export default {
  name: "HomeView",

  components: {
    dataInfo,
  },
  data() {
    return{
      commit: [],
    }
  },
    async mounted() {
      const get = await axios.get(
        "https://api.github.com/repos/vuejs/vue/commits"
      );
      this.commit = get.data;
      console.log(this.commit);
    },
};
</script>

<style scoped>
body{
  margin: 0 !important;
}
</style>
