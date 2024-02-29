<template>
    <v-list two-line subheader>
        <v-subheader>
            <v-container direction="row" class="custom-flex-container">
                <div class="custom-flex-container">
                    <v-img width="30" height="23" src="@/assets/box.svg" />
                    <p class="text panel-text px-3">Transações recentes</p>
                    <p class="text date-text">últimos 7 dias</p>
                </div>
                <a class="see-all-link">Ver tudo</a>
            </v-container>
        </v-subheader>

        <v-list-item v-for="(transaction, index) in transactions" :key="index">
            <v-divider color="#202027" thickness="2px" />
            <v-list-item-content class="list-item-wrapper direction">
                <div class="list-item-wrapper">
                    <div class="icon-wrapper mt-2" :style="{ backgroundColor: transaction.iconColor }">
                        <v-img width="17" height="17" src="@/assets/shop.svg" />
                    </div>
                    <v-list-item-title class="list-item mt-2">{{ transaction.name }}</v-list-item-title>
                </div>
                <v-list-item-title class="list-item mr-2">
                    R$ {{ transaction.amount.toFixed(2).replace('.', ',') }}
                </v-list-item-title>
            </v-list-item-content>
        </v-list-item>
        <v-divider color="#202027" thickness="2px" />
    </v-list>
</template>
  
<script>
export default {
    name: 'TransactionsList',
    data() {
        return {
            transactions: [
                { name: 'Mercadinho da Cidade', amount: 10.98, iconColor: '#FDFF9D' },
                { name: 'Tenda Nostra', amount: 26.38, iconColor: '#FF9D9D' },
                { name: 'Farmácia Um', amount: 43.17, iconColor: '#C8FF9D' },
                { name: 'Academia Body', amount: 62.12, iconColor: '#AB9DFF' },
                { name: 'ShopOnline', amount: 135.24, iconColor: '#FF9DEF' }
            ]
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
</style>
  