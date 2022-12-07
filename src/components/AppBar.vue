<template>
  <v-app-bar app color="#ffffff" dark class="nav-bar">
    <div class="d-flex align-center">
      <v-img
        alt="Company Logo"
        class="shrink mr-2"
        contain
        src="@/assets/company-logo.svg"
        transition="scale-transition"
        width="150"
      />
    </div>

    <v-spacer></v-spacer>

    <v-btn
      color="red"
      icon
      text
      ><v-badge color="#C92F02"  content="6" overlap>
        <img src="@/assets/bell.svg" width="16" />
      </v-badge>
    </v-btn>

    <div class="d-flex align-center ml-14">
      <v-avatar class="mr-4">
        <img src="@/assets/user.svg" alt="John" />
      </v-avatar>
      <div>
        <p class="nav-bar-username mb-1">{{ name }}</p>
        <p class="nav-bar-user-role mb-0">{{ role }}</p>
      </div>
    </div>
  </v-app-bar>
</template>
<script>
export default {
  data () {
    return {
      name: 'Kalu Abasiama',
      role: 'Admin'
    }
  }
}
</script>
