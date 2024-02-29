<template>
    <v-list two-line subheader>
        <v-subheader>
            <v-container direction="row" class="custom-flex-container">
                <div class="custom-flex-container">
                    <v-img width="30" height="23" src="@/assets/story.svg" />
                    <p class="text panel-text px-3">Análise geral</p>
                    <p class="text date-text">últimos 7 dias</p>
                </div>
                <a class="see-all-link">Ver tudo</a>
            </v-container>
        </v-subheader>
        <v-divider color="#202027" thickness="2px" />
        <div class="cash-flow-wrapper">
            <div>
                <p class="list-item-paragraph">{{ cashFlow.gains.name }}</p>
                <p class="panel-text">R${{ cashFlow.gains.amount }}</p>
            </div>
            <div>
                <p class="list-item-paragraph">{{ cashFlow.losses.name }}</p>
                <p class="panel-text">R${{ cashFlow.losses.amount }}</p>
            </div>
        </div>
        <v-divider color="#202027" thickness="2px" />
        <v-list-item v-for="(transaction, index) in analysisData" :key="index">
            <v-list-item-content class="list-item-wrapper direction">
                <div class="list-item-wrapper">
                    <div class="icon-wrapper mt-2" :style="{ backgroundColor: transaction.iconColor }">
                        <v-img width="17" height="17" src="@/assets/shop.svg" />
                    </div>
                    <v-list-item-title class="list-item mt-2">{{ transaction.name }}</v-list-item-title>
                </div>
                <v-list-item-title class="list-item">
                    {{ transaction.amount }} %
                </v-list-item-title>
            </v-list-item-content>
            <v-progress-linear v-model="transaction.amount" :buffer-value="bufferValue" :color="transaction.color"
                class="mt-1 mb-1" />
        </v-list-item>
    </v-list>
</template>
  
<script>
export default {
    name: 'GeneralAnalysis',
    data() {
        return {
            analysisData: [
                { name: 'Compras', amount: 62, color: '#FF9999' },
                { name: 'Boletos', amount: 14, color: '#A799FF' },
                { name: 'Investimentos', amount: 5, color: '#FF99D6' },
            ],
            cashFlow: {
                gains: { name: 'Ganhos', amount: 2789.21 },
                losses: { name: 'Saidas', amount: 1278.47 },
            }
        };
    }
};
</script>
  
<style>
.custom-flex-container {
    display: flex;
    margin: 0 !important;
    justify-content: space-between;
    align-items: center;
}

.list-item {
    font-size: 14px !important;
    color: black !important;
    line-height: 21px !important;
    font-weight: 500 !important;
    margin-left: 12px;
}

.list-item-paragraph {
    font-size: 14px !important;
    color: black !important;
    line-height: 21px !important;
    font-weight: 500 !important;
    margin-bottom: 2px;
}


.list-item-wrapper {
    display: flex;
    align-items: center;
}

.direction {
    justify-content: space-between;
}

.date-text {
    color: #A3A3A3;
    font-size: 14px;
    line-height: 21px;
}

.panel-text {
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
    color: '#202027'
}

.see-all-link {
    color: #7986FE
}

.icon-wrapper {
    width: 32px;
    height: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.cash-flow-wrapper {
    display: flex;
    justify-content: space-between;
    margin: 10px 20px;
}
</style>
  