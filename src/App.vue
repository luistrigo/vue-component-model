<template>
  <div class="title">
    <h3>Test components with v-model inside</h3>
  </div>
  <div class="container">
    <TextPassword v-model="password"></TextPassword>
    Result: {{ password }}
    <TextPassword hideEye v-model="password" textClass="focus"></TextPassword>
  </div>
</template>

<script>
import TextPassword from "./components/TextPassword.vue";

export default {
  name: "App",
  components: {
    TextPassword,
  },
  data() {
    return {
      password: "",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  margin: 0 auto;
  max-width: 300px;
}
input[type="text"],input[type="password"]{
  border: 1px solid #ccc;
  border-radius: 5px;
  line-height: 1.5em;
  font-size: 1.2em;
}
</style>
