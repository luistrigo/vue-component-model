<template lang="en">
<div class="content-password">
    <input :type="typeInput" :class="textClass" :value="modelValue" @input="changePassword($event.target.value)"/>
    <a v-if="!hideEye" @click="toggleTypeInput" href="#"><img :src="imagePass"></a>
</div>
</template>
<script>
export default {
  props: {
    modelValue: String,
    hideEye: Boolean,
    textClass: String,
  },
  emits: ["update:modelValue"],
  data() {
    return {
      typeInput: "password",
    };
  },
  methods: {
    changePassword(value) {
      this.$emit("update:modelValue", value);
    },
    toggleTypeInput() {
      this.typeInput = this.typeInput === "text" ? "password" : "text";
    },
  },
  computed: {
    imagePass() {
      return this.typeInput === "text"
        ? require("../assets/eye_close.png")
        : require("../assets/eye_open.png");
    },
  },
};
</script>
<style scoped>
.content-password {
  position: relative;
}
.content-password input {
  position: relative;
  width: 100%;
}
.content-password a {
  position: absolute;
  right: -5px;
  top: 6px;
  
}
.focus:hover,
.focus:focus {
  background-color: bisque;
}
</style>