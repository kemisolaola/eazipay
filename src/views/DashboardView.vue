<template>
  <v-container fluid>
    <v-row justify='center'>
      <v-col cols='12' md='11'>
        <h2>Welcome {{ lastName }}</h2>
        <h6>Pay and manage your employee in minutes</h6>
        <v-row class='mt-10' justify="space-between">
          <v-col cols='12' md='9' class='mt-'>
            <!-- Wallet Card -->
            <v-card class='blue-gradient pa-8 white--text' rounded='lg'>
              <v-row justify='space-between' align-content='center'>
                <v-col cols='4'>
                  <p class='mb-1'>Wallet Balance</p>
                  <h2>N12,560,078.00</h2>
                </v-col>
                <v-col cols='2'>
                  <v-btn
                    class='mt-5 text-capitalize fund-wallet-btn'
                    dark
                    elevation='0'
                  >
                    Fund Wallet
                  </v-btn>
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
          <v-col md='2'>
            <div class="active-container">
              <div class='active-loan'>
                <p class='text-center white--text py-1 mb-0'>Active loans</p>
              </div>
              <div class="text-center active-loan-div">
                <p class="next-payment mb-1">Next Repayment</p>
                <p class="date mb-1">Septermber 20,2022</p>
                <p class="amount">N100,000.00</p>
              </div>
              <div class="text-center mt-9 pb-4 px-3">
                <p class="total-employ mb-1">Total Employee</p>
                <p class="total-value text-left pl-3">50</p>
                <v-progress-linear value="30" class="px-4" height="8" color="#0A244F"></v-progress-linear>
                <div class="pt-1 gender d-flex justify-space-between">
                  <p>Male</p>
                  <p>Female</p>
                </div>
              </div>
            </div>
          </v-col>
        </v-row>
        <v-row class='mt-10'>
          <v-col cols='12'>
            <v-row justify='center'>
              <v-col cols='10'>
                <v-img src='@/assets/graph.svg'></v-img>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols='12' md='11'>
        <h2>Recent Activities</h2>
        <v-row no-gutters>
          <v-col cols="11" class="px-0">          <input  dense class='search-input'/>
</v-col>
<v-col class="px-0">
          <v-btn elevation='0' color='#E4572E' class='search-btn'>
            <v-icon color='white'>mdi-magnify</v-icon>
          </v-btn>
          </v-col>
        </v-row>
        <div class="dashboard-container">
          <table class="dashboard-table">
            <tr>
              <td>Name</td>
              <td>Details</td>
              <td>Date</td>
              <td>Time</td>
              <td>Status</td>
            </tr>
            <tr class="dashboard-table-row" v-for="i in 60" :key="i">
            <td>Adewale</td>
            <td>Adewale</td>
            <td>Adewale</td>
            <td>Adewale</td>
            <td class="primary--text">Adewale</td>
          </tr>
        </table>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {
      adminActions: [
        {
          img: require('@/assets/admin/add-employee.svg'),
          text: 'Add Employee'
        },
        {
          img: require('@/assets/admin/run-payroll.svg'),
          text: 'Run Payroll'
        },
        {
          img: require('@/assets/admin/quick-loan.svg'),
          text: 'Quick Loan'
        },
        {
          img: require('@/assets/admin/inventory.svg'),
          text: 'Inventory'
        }
      ]
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
.active-container {
  background: #FFFFFF;
border: 1px solid #FFFFFF;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
}
.active-loan {
  background: #e4572e;
  box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.1);
  border-radius: 16px 16px 0px 0px;
}
.next-payment{
  font-size: 11px;
line-height: 14px;
color: #5F5F5F;

}
.active-loan-div {
  background: #FFFFFF;
border: 1px solid #FFFFFF;
box-shadow: 0px 4px 25px rgba(0, 0, 0, 0.05);
border-radius: 0 0 16px 16px;

}
.date {
  font-size: 13px;
color: #5F5F5F;
}
.amount{
  font-weight: 700;
font-size: 16px;
color: #E4572E;
}
.total-employ{
  font-weight: 500;
font-size: 14px;
color: #5F5F5F;
}
.total-value {
  font-weight: 900;
font-size: 27px;
line-height: 30px;
color: #444444;
}
.gender{
  font-weight: 600;
font-size: 9px;
line-height: 12px;
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
  height: 42px !important;
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
</style>
