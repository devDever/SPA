<template>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">
      <router-link to="/"> SPA </router-link>
    </b-navbar-brand>

    <b-navbar-nav class="ml-auto">
      <router-link tag="li" to="/" exact active-class="active">
        <a href="#">Create</a>
      </router-link>
      <router-link tag="li" to="/List" active-class="active">
        <a href="#"> List</a>
      </router-link>
      <router-link tag="li" to="/task/1" active-class="active">
        <a href="#"> Task</a>
      </router-link>
    </b-navbar-nav>
  </b-navbar>
</template>

<style lang="scss" scope>
a {
  color: #fff;
  margin-right: 20px;
}
</style>
