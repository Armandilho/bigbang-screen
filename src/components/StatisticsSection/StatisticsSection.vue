<template>
    <v-container>
        <v-row justify="space-between">
            <v-col class="pr-3 col" sm="12" md="6">
                <transaction-list />
            </v-col>
            <v-col class="pl-3 col" sm="12" md="6">
                <general-analysis />
            </v-col>
        </v-row>
    </v-container>
</template>
  
  
<script>

import TransactionList from './TransactionList/TransactionList.vue'
import GeneralAnalysis from './GeneralAnalysis/GeneralAnalysis.vue'

export default {
    name: 'StatisticsSection',
    data: () => ({
        totalBalance: '304,78',
    }),
};
</script>
  
<style scoped>
.main-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.text {
    color: white;
}

.total {
    font-size: 20px;
}

.value {
    font-size: 36px;
}

.display {
    display: flex;
    align-items: center;
}

.spacing {
    margin-right: 12px;
}

.buttonIcon {
    align-self: baseline;
}

.panel-text {
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
}

.date-text {
    color: #A3A3A3;
    font-size: 14px;
    line-height: 21px;
}

.custom-flex-container {
    display: flex;
    width: 400px;
    margin: 0;
    justify-content: space-between;
    align-items: center;
}

.col {
    max-width: 540px;
}
</style>
  