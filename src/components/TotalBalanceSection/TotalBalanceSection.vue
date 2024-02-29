<template>
  <v-container>
    <v-container class="main-container">
      <v-row justify="space-between">
        <v-col md="8" sm="12">
          <p class="text font-weight-medium total">Saldo Total</p>
          <div class="display">
            <p class="text value spacing">R${{ totalBalance }}</p>
            <v-icon icon="fas fa-bolt spacing" color="#FFF500" size="small" />
            <p class="text spacing">rendendo 124%</p>
          </div>
        </v-col>
        <v-col md="4" sm="12" class="buttons-container">
          <v-btn class="text-none text-subtitle-1 spacing" color="#7986FE" size="small" variant="flat" height="40px"
            width="250px">
            <v-row justify="space-between" align="center">
              <v-col md="3">
                <v-btn flat icon size="small" variant="contained">
                  <v-icon icon="fa fa-paper-plane" class="buttonIcon" />
                </v-btn>
              </v-col>
              <v-col>Enviar Dinheiro</v-col>
            </v-row>
          </v-btn>
          <v-btn class="text-none text-subtitle-1" color="#7986FE" size="small" variant="flat" height="40px" width="56px">
            <v-icon icon="fa-solid fa-plus" />
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="custom-flex-container">
      <v-img width="12" height="24" src="@/assets/bubble.svg" />
      <p class="text panel-text mx-4">Painel de estatísticas</p>
      <p class="text date-text">últimos 7 dias</p>
    </v-container>
    <v-container>
      <v-row no-gutters justify="space-between">
        <v-col v-for="cardContent in cardsContents" :key="cardsContents.value" cols="12" sm="12" md="12" lg="4"
          class="col-width mb-3">
          <total-balance-card :value=cardContent.value :title=cardContent.title />
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
import TotalBalanceCard from './TotalBalanceCard/TotalBalanceCard.vue';
export default {
  name: 'TotalBalanceSection',
  data: () => ({
    totalBalance: '304,78',
    cardsContents: [
      { title: 'Conta PJ', value: 'R$39,882' },
      { title: 'Recebimentos', value: 'R$765,88' },
      { title: 'Lucro', value: 'R$15,887' },
    ]
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
  max-width: 400px;
  margin: 0;
  justify-content: space-between;
  align-items: center;
}

.col-width {
  max-width: 352px;
}

.buttons-container {
  display: flex;
  justify-content: end;
}
</style>
