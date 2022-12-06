<template>
    <div>
        <small>Settings / <span class="pointer">{{routeName}}</span></small>
          <h2>Settings</h2>
          <div class="d-flex justify-center align-center">
            <router-link :to="link.to" active-class="py-5 white--text active-sub-route" v-for="(link, index) in settingActions" :key="index" > <span class="px-5 sub-route pointer">{{link.name}}</span></router-link>
          </div>
    </div>
</template>
<script>
export default {
  props: ['routeName'],
  data () {
    return {
      settingActions: [
        { name: 'Profile', to: '/profile' },
        { name: 'Manage Account', to: '/settings/manage-account' },
        { name: 'Business File', to: '/settings/business-profile' },
        { name: 'Team', to: '/team' },
        { name: 'Security', to: '/security' },
        { name: 'Refer', to: '/refer' }
      ]
    }
  }
}
</script>
<style scoped>
a{
    text-decoration: none;
    color: #444444 !important;
}
.sub-route{
font-weight: 400;
font-size: 14px;
line-height: 19px;
/* color: #444444 !important; */
  }
  .active-sub-route {
font-weight: 500;
line-height: 19px;
color: #FCFCFC;
background: #0A244F;
border: 1px solid #FCFCFC;
border-radius: 8px;
  }
</style>
