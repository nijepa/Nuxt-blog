<template>
  <div class="admin-page">
    <section class="new-post">
      <AppButton @click="$router.push('/admin/new-post')">Create Post</AppButton>
      <AppButton class="logout" @click="onLogout">Logout</AppButton>
    </section>
    <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList
        isAdmin
        :posts="loadedPosts" />
    </section>
  </div>
</template>

<script>
export default {
  layout: "admin",
  middleware: ["check-auth", "auth"],
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts;
    }
  },
  methods: {
    onLogout() {
      this.$store.dispatch("logout");
      this.$router.push("/admin/auth");
    }
  }
};
</script>

<style scoped>
.admin-page {
  padding: 20px;
}

.new-post {
  text-align: center;
  border-bottom: 2px solid rgb(99, 173, 235);
  padding-bottom: 10px;
}

.logout {
  float: right;
  background-color: rgb(214, 69, 69);
  /* margin-left: 10px */
}

.existing-posts h1 {
  text-align: center;
}
</style>
