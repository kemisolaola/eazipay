<template>
    <v-container fluid>
      <v-row justify='center'>
        <v-col cols='12' md='11'>
            <setting-nav :routeName="name"/>
          <v-row class='mt-10' justify="center">
            <v-col cols='12' md='11' class='mt-'>
              <!-- Wallet Card -->
              <v-card class='settings-card pa-8' rounded='lg'>
                <div class="d-flex justify-space-between align-center">
                    <p class="manage-role font-weight-bold text-left">Manage Roles</p>
                    <v-icon>mdi-close-circle-outline</v-icon>
                </div>
                <v-divider class="mb-6"></v-divider>
                <v-row>
                  <v-col cols="2">
                    <div class="roles-title">
                      <p class="text-uppercase default-role white--text pl-2">default Roles</p>
                    <p v-for="(role, index) in roleTitle" :key="index" class="pl-2">{{role}}</p>
                    </div>
                    <p class="roles-title font-weight-bold pl-2 mt-9">Custom Roles</p>
                    <p class="head-account pa-2">Head Account</p>
                    <p class="create-role-info pl-2">You can create your own custom roles, and choose exactly what team members can see and do.</p>
                    <v-btn class="text-capitalize create-role-btn py-4" color="#e4572e" elevation="0" dark x-small> <span><v-icon>mdi-plus</v-icon></span> Create New Role</v-btn>
                  </v-col>
                  <v-col>
                    <div class="d-flex justify-space-between">
                      <p class="head-account-title" >Head Account</p>
                      <v-btn class="text-capitalize" color="#E4572E" dark small elevation="0" >Edit <span><v-icon small>mdi-pencil-outline</v-icon></span></v-btn>
                    </div>
                    <p class="head-info">Head make sure that financial reports are up-to-date and compliant with standards. They produce periodic activity updates for top management and an annual budget proposal.</p>
                    <p class="role-info">Team Members with the role</p>
                    <div class="d-flex ">
                      <div class="px-1 team-member-div px-2 py-1 mr-4" v-for="(name, i) in teamMembers" :key="i">
                        <p class="team-members mb-0 mt-1"><v-avatar size="25">
                          <img src="@/assets/members.svg" alt="" />
                        </v-avatar> {{name}}</p>
                      </div>
                    </div>
                    <v-row class="mt-7">
                      <v-col cols="6">
                        <v-card tile elevation="0" color="#0A244F" dark class="text-center">
                          <p>What Role Can Access</p>
                        </v-card>
                        <div v-for="(action, index) in canDo" :key="index" class="px-6 d-flex justify-space-between">
                          <p class="role-access-list mb-3">{{action}}</p>
                          <v-icon color="#19A301">mdi-check</v-icon>
                        </div>
                      </v-col>
                      <v-col cols="6">
                        <v-card tile elevation="0" color="#E4572E" dark class="text-center">
                          <p>What Role Can Access</p>
                        </v-card>
                        <div v-for="(action, index) in cantDo" :key="index" class="px-6 d-flex justify-space-between">
                          <p class="role-access-list mb-3">{{action}}</p>
                          <v-icon color="#DE1C10">mdi-close</v-icon>
                        </div>
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-card>

              <!-- Admin Actions -->
              <v-row class='mt-12'>
                <v-col
                  cols='12'
                  md='3'
                  v-for='(action, index) in adminActions'
                  :key='index'
                >
                  <v-card
                    color='#023C98'
                    width='100%'
                    height='125'
                    class='pt-3'
                    rounded='lg '
                  >
                    <v-img
                      :src='action.img'
                      width='50'
                      height='50'
                      class='mx-auto my-auto'
                    ></v-img>
                    <p class='text-center white--text pt-3'>{{ action.text }}</p>
                  </v-card>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </template>

<script>
import SettingNav from '@/components/SettingNav.vue'
import { mapState } from 'vuex'
export default {
  components: { SettingNav },
  data () {
    return {
      name: 'Manage Account',
      roleTitle: ['Admin', 'Assistant', 'Auditor'],
      canDo: ['Add Bonus and Deduction', 'Add Compliance', 'Edit Compliance', 'Transaction History', 'Fund Wallet', 'Manage Inventory', 'Manage Invoice', 'Manage Receipt', 'Book Keeping Settings'],
      cantDo: ['Purchase or Change Plan', 'Add Employee ', 'Edit Employee', 'Add Salary', 'Edit Salary', 'Run Payroll', 'Archive Employee', 'Pay Compliance', 'Fund Wallet', 'Withdraw from Wallet', 'Manage Account', 'Manage Business Profile', 'Manage Team'],
      teamMembers: ['Ada Okonye', 'Edward Madaki', 'Adekule Ajasin', 'Zainab Muhammad']
    }
  },
  computed: {
    ...mapState(['lastName'])
  }
}
</script>
  <style scoped>
  .fund-wallet-btn {
    background: rgba(12, 25, 47, 0.6) !important;
    border-radius: 8px;
  }
  .active-loan {
    background: #e4572e;
    box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.1);
    border-radius: 0px 16px 16px 0px;
  }
  .search-input {
    border: 1px solid #b9bbc0;
    border-radius:  16px 0px 0px 16px;
    width: 100%;
    height: 40px;
    padding: 20px;
  }
  .search-btn{
    border-radius: 0px 16px 16px 0px;
    height: 40px !important;
  }
  .dashboard-table {
    background: inherit;
    width: 100%;
    height: 300px;
  }
  .dashboard-container {
    background: inherit;
    height: 300px;
    overflow: hidden;
  }

  .dashboard-table-row {
    background: #FFFFFF;
  border: 1px solid #B9BBC0 !important;
  border-radius: 16px !important;
  padding: 20px !important;
  height: 30px;
  margin-bottom: 50px !important;
  }
  .settings-card{
    background: #FFFFFF;
border: 1px solid #E0E0E0;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
border-radius: 16px;

  }

  .manage-role {
    font-weight: 500;
font-size: 25px;
line-height: 38px;
color: #444444;
  }
  .roles-title {
    font-size: 12px;
line-height: 19px;
color: #8B8B8B;
  }
  .default-role {
    background-color:  #023C98;;
  }
  .head-account {
font-weight: 700;
font-size: 13px;
line-height: 19px;
color: #E4572E;
background: #FFF0EC;  }
.create-role-info {
font-weight: 500;
font-size: 10px;
line-height: 12px;
color: #555555;
}
.create-role-btn {
  background: #E4572E;
border: 1px solid #DE1C10;
border-radius: 8px;
}
.head-account-title {
  font-size: 28px;
line-height: 38px;
color: #E4572E;

}
.head-info {
font-weight: 500;
font-size: 14px;
line-height: 16px;
color: #444444;
}
.role-info {
  font-weight: 500;
font-size: 14px;
line-height: 16px;
  color: #231f1f !important;
}
.team-members {
  font-weight: 500;
font-size: 12px;
letter-spacing: -0.019em;
color: #444444;
}
.team-member-div{
  background: #FFF0EC;
border: 1px solid #9B9B9B;
border-radius: 8px;
}
.role-access-list {
  font-weight: 500;
font-size: 14px;
color: #444444;
}
  </style>
