<template>
  <div>
    <h1>I am form footer</h1>

    <hr>

    <h2>THis is my event</h2>
    {{test}}
  </div>
</template>

<script>
import { bus } from "../main";
export default {
  data() {
    return {
      test: "Test"
    };
  },
  methods: {},
  created() {
    bus.$on("ListChanged", data => {
      this.test = data;
    });
  }
};
</script>
