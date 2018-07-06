<template>
  <div id="container">
    <user-form></user-form>
  </div>
</template>

<script>
import UserForm from './components/UserForm.vue';
export default {
 components: {
   UserForm: UserForm
 }
}
</script>

<style lang="scss" scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
