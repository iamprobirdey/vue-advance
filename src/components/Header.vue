<template>
  <div>
    <nav>
      <ul>
        <li @click="changeMyList">{{title}}</li>
        <li>Contact us</li>
        <li>About us</li>
      </ul>
    </nav>
  </div>
</template>
<script>
import { bus } from "../main";
export default {
  data() {
    return {
      test: "Hii",
      title: "Home"
    };
  },
  methods: {
    changeMyList() {
      this.title = "Hommy";
      bus.$emit("ListChanged", "Anukul Thakur");
    }
  }
};
</script>
<style>
nav {
  background-color: #4f4f4f;
}

/* nav ul{
        float: left;
    } */

nav ul li {
  display: inline-block;
  color: aliceblue;
  margin: 5px;
}
</style>
