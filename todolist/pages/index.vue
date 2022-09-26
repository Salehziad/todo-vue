<template>
  <div>
    <Home />
  </div>
</template>

<script>
import Home from "../components/Home";
export default {
  name: "App",
  components: {
    Home,
  },

};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
</style>
