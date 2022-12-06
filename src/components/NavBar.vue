<template>
  <v-navigation-drawer v-model="navDrawer" app color="white">
<div class="logo-container blue-gradient d-flex align-center justify-center">
    <img src="@/assets/eazipay.svg" alt="" height="45%">
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
</style>
