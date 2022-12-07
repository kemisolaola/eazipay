<template>
  <v-navigation-drawer v-model="navDrawer" app color="white">
<div class="logo-container blue-gradient d-flex align-center justify-center">
    <img src="@/assets/eazipay.svg" alt="" height="45%">
</div>
<div class="mt-7">
  <router-link to="/" class="d-flex align-center justify-center" active-class="active">
    <img class="pr-2" src="@/assets/home-icon.svg"/>
      <p class="text-center mb-0">DASHBOARD</p>
    </router-link>
    <v-divider class="mt-3"></v-divider>
</div>
  </v-navigation-drawer>
</template>
<script>
export default {
  data () {
    return {
      navDrawer: true
    }
  }
}
</script>
<style scoped>
.logo-container {
    height: 150px;
}
.active{
  color: #E4572E
}
a {
  text-decoration: none;
  font-weight: 700;
font-size: 16px;
line-height: 19px;
}
</style>
