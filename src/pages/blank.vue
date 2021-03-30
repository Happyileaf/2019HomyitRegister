<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "HelloWorld"
    };
  }
};
</script>

<style scoped>
h1 {
  font-size: 16px;
  font-weight: normal;
}
</style>