<template>
  <div id="app">
    <firstHeader />
    <Users v-bind:users="users" />
  </div>
</template>

<script>
import Users from "./components/Users";
import firstHeader from "./components/firstHeader";
import axios from "axios";

export default {
  name: "app",
  components: {
    firstHeader,
    Users
  },
  data() {
    return {
      users: []
    };
  },
  created() {
    axios
      .get("https://my-user-manager.herokuapp.com/users")
      .then(res => (this.users = res.data))
      // eslint-disable-next-line no-console
      .catch(err => console.log(err));
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
