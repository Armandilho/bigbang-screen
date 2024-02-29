<template>
  <v-container class="background">
    <v-row>
      <v-col cols="12">
        <navbar />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <total-balance-section />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <statistics-section />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import TotalBalanceSection from './TotalBalanceSection/TotalBalanceSection.vue';
import Navbar from './Navbar/Navbar.vue'
import StatisticsSection from './StatisticsSection/StatisticsSection.vue'
// import StatisticsPanel from './StatisticsPanel.vue';
// import RecentTransactions from './RecentTransactions.vue';
// import OverallAnalysis from './OverallAnalysis.vue';

export default {
  name: 'DashboardLayout',
  components: {
    TotalBalanceSection,
    Navbar,
    StatisticsSection,
  }
}
</script>

<style scoped>
.background {
  background: linear-gradient(to bottom, #202027 0%, #202027 50%, #FFF 50%, #FFF 100%);
  height: 100vh;
  width: 100%;
  max-width: 100%;
}
</style>
