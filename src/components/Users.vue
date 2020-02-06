<template>
  <div class="content">
    <Header />
    <div v-bind:key="user.id" v-for="user in users" class="user-content">
      <usersList v-bind:user="user" />
      <button class="btn2" v-on:click="userDetail(user)">Details</button>
    </div>

    <div class="users-detail">
      <h4>User Detail</h4>
      <p v-if="msgDisplay">
        Please click on the Details button to view the user's information.
      </p>
      <div v-else>
        <p>Id: {{ Id }}</p>
        <p>Name: {{ name }}</p>
        <p>Email: {{ email }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./Header";
import usersList from "./usersList";

export default {
  name: "Users",
  components: {
    Header,
    usersList
  },
  data() {
    return {
      Id: 0,
      name: "",
      email: "",
      msgDisplay: true
    };
  },
  methods: {
    userDetail(user) {
      this.Id = user.id;
      this.name = user.name;
      this.email = user.email;
      this.msgDisplay = false;
    }
  },
  props: ["users"]
};
</script>

<style scoped>
.content {
  width: 40%;
  margin-left: 30%;
  border-radius: 5px;
  border: 1px solid rgb(188, 192, 236);
  background-color: rgb(242, 242, 247);
}
h4 {
  height: 25px;
  padding: 5px 5px 1px 10px;
  background-color: rgb(166, 170, 194);
}
.btn2 {
  float: right;
  width: 10%;
  margin-top: 5px;
  margin-right: 10px;
}
.user-content {
  height: 35px;
  border-bottom: 1px solid rgb(188, 192, 236);
}
.users-detail {
  margin: 20px 10px 20px 10px;
  width: 80%;

  border-radius: 5px;
}
p {
  padding: 7px;
  color: rgb(97, 5, 100);
  font-family: sans-serif;
}
</style>
