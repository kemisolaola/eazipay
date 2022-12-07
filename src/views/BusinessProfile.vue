<template>
    <v-container fluid>
      <v-row justify='center'>
        <v-col cols='12' md='11'>
            <setting-nav :routeName="name"/>
          <v-row class='mt-10' justify="center">
            <v-col cols='12' md='11' class='mt-'>
              <!-- Wallet Card -->
              <div class='pa-8' rounded='lg'>
                <v-row no-gutters>
                  <v-col cols="2" class="pr-0">
                    <div class="roles-title mt-3">
                    <p v-for="(role, index) in roleTitle" :key="index" @click="selectRole(index)" class="pl-2 py-2 pointer" :class="selectedRole === index ? 'role-active' : '' ">{{role}}</p>
                    </div>
                    </v-col>
                  <v-col >
                    <v-card class='settings-card pa-8' rounded='lg'>
                    <div class="d-flex justify-space-between">
                      <p class="management-role font-weight-bold text-left">Business Owner/CEO/Founder</p>
                      <v-btn class="text-capitalize" color="#E4572E" dark small elevation="0" outlined> <span><v-icon small>mdi-plus</v-icon></span>Add More</v-btn>
                    </div>
                    <v-divider class="mb-6"></v-divider>
                    <v-card v-for="(head, index) in companyHead" :key="index" class="mb-4 business-container" outlined :color="head.color">
                     <v-row>
                      <v-col cols="3" class="pa-5">
                        <img :src="head.img" alt="">
                          <button class="upload-btn mt-8 ml-2"> <span><v-icon color="white" class="pr-1">mdi-tray-arrow-up</v-icon></span> Upload</button>
                          <button class="close-btn mt-8 ml-2"> <span><v-icon color="#ffffff99" class="pr-1">mdi-close-circle-outline</v-icon></span>Cancel</button>
                      </v-col>
                      <v-col>
                        <div class="personal-info pl-6 pt-3">
                          <div style="position: relative">
                            <div class="d-flex justify-space-between">
                              <p class="info-name mb-2">{{head.name}}</p>
                              <v-icon class="info-name mb-2 pointer" @click="selectMenu(index)" color="#8B8B8B">mdi-dots-vertical</v-icon>
                              <div class="menu-items" v-if="(selectedMenu === index)">
                                <p style="background: #023C98" class="py-1 mb-1 pl-2 white--text">Edit</p>
                                <p class="mb-0 pl-2 py-1">Remove</p>
                              </div>
                            </div>
                          <p class="contact-info mb-1"><span class="contact-info-title">Email:</span>{{head.email}}</p>
                          <p class="contact-info  mb-1"><span class="contact-info-title">Phone Number:</span>{{head.phone}}1</p>
                          <p class="contact-info  mb-1"><span class="contact-info-title">BVN:</span> {{head.bvn}}</p>
                          <p class="contact-info  mb-1"><span class="contact-info-title">House Address:</span> {{head.address}}</p>
                        </div>
                        <div class="id-means mt-8 pa-6">
                          <p class="text-center identity-means-text">Means of Identification</p>
                          <div class="d-flex justify-center">
                            <img :src="head.imgPassport" alt="">
                          </div>
                        </div>
                        </div>
                      </v-col>
                     </v-row>
                    </v-card>
                    </v-card>
                  </v-col>
                </v-row>
              </div>
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
      name: 'Business Profile',
      selectedRole: 1,
      roleTitle: ['Company', 'CEO/Founder', 'Company Directors', 'Account Information', 'Branch/Department'],
      companyHead: [
        {
          name: 'Tiamiyu Wasiu Oladimeji',
          email: 'tmwasiu7@gmail.com',
          phone: '08160178711',
          bvn: '8160178711',
          color: '#023c98',
          address: '16, Adebanjo Ammed Street, Ajah',
          img: require('@/assets/ceo1.png'),
          imgPassport: require('@/assets/passports.png')
        },
        {
          name: 'Ejiro Odiamakwu Kelvin',
          email: 'tmwasiu7@gmail.com',
          phone: '08160178711',
          bvn: '8160178711',
          color: '#8B8B8B',
          address: '16, Adebanjo Ammed Street, Ajah',
          img: require('@/assets/ceo2.png'),
          imgPassport: require('@/assets/passport2.png')
        },
        {
          name: 'Aderonke Emmanuel Victor',
          email: 'tmwasiu7@gmail.com',
          phone: '08160178711',
          bvn: '8160178711',
          color: '#E0A409',
          address: '16, Adebanjo Ammed Street, Ajah',
          img: require('@/assets/ceo3.png'),
          imgPassport: require('@/assets/passport3.png')

        }
      ],
      menu: false,
      selectedMenu: null
    }
  },
  computed: {
    ...mapState(['lastName'])
  },
  methods: {
    selectRole (index) {
      this.selectedRole = index
    },
    selectMenu (index) {
      this.menu = !this.menu
      this.selectedMenu = index
    }
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

  .management-role {
    font-weight: 500;
font-size: 25px;
line-height: 38px;
color: #444444;
  }
  .roles-title {
    font-size: 13px;
line-height: 20px;
color: #444444;
  }
  .role-active{
    background: #FFFFFF;
border: 1px solid #E0E0E0;
color: #E4572E;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
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
.business-container{
border: 1px solid #E0E0E0;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
border-radius:16px;
padding: 1px;
}
.personal-info{
  background: #FFFFFF;
border: 1px solid #E0E0E0;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
border-radius: 0px 16px 16px 0px;
padding: 2px;
}
.info-name{
  font-size: 24px;
line-height: 28px;
color: #0A244F;
}
.contact-info{
  font-weight: 500;
font-size: 14px;
line-height: 19px;
color: #444444;

}
.contact-info-title{
  color: #8B8B8B;
}
.id-means {
  background: #F7F8FF;
border-radius: 0px 0px 8px 8px;
}
.identity-means-text{
  font-size: 16px;
line-height: 19px;
color: #444444;
font-weight: 500;
}
.upload-btn {
  width: 131px;
height: 56px;
background: rgba(255, 255, 255, 0.3);
border: 1px solid rgba(185, 187, 192, 0.5);
border-radius: 8px;
font-weight: 500;
font-size: 14px;
line-height: 19px;
color: #FFFFFF;
}
.close-btn {
  width: 131px;
height: 56px;
background: inherit;
border: 1px solid rgba(185, 187, 192, 0.5);
border-radius: 8px;
font-weight: 500;
font-size: 14px;
line-height: 19px;
color: #ffffff99;}
.menu-items{
  width: 100px;
  background: #fff;
  position: absolute;
  right: 0;
  top: 25px;
  font-weight: 500;
font-size: 13px;
line-height: 16px;
  box-shadow: -4px 2px 10px rgba(0, 0, 0, 0.15);
}
  </style>
