<template>
  <div class="list">
    <a>{{ user.name }}</a>
  </div>
</template>
<script>
export default {
  name: "usersList",
  props: ["user"],
  methods: {
    userDetail() {}
  }
};
</script>
<style scoped>
.list {
  display: flex;
  width: 80%;
  padding: 10px 10px 10px 20px;
  font-weight: 600;
  border-radius: 0;
  float: left;
}
</style>
