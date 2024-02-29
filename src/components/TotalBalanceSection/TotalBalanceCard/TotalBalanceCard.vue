<template>
    <v-card height="210" class="card">
        <v-card-title class="title">
            {{ title }}
        </v-card-title>
        <v-card-text>
            <v-container>
                <v-row>
                    <v-col cols="12">
                        <h1 class="value">{{ value }}</h1>
                    </v-col>
                </v-row>
            </v-container>
        </v-card-text>
        <div class="wrapper">
            <v-btn variant="outlined" width="70%">
                Ver mais detalhes
            </v-btn>
            <v-btn variant="outlined"><v-icon icon="fa-solid fa-bars" /></v-btn>
        </div>
    </v-card>
</template>
  
<script>
export default {
    name: 'TotalBalanceCard',
    props: {
        value: {
            type: String,
            required: true,
        },
        title: {
            type: String,
            required: true,
        }
    },
};
</script>
  
<style scoped>
.card {
    box-shadow: 0px 7px 29.700000762939453px 0px #00000012;
}

.title {
    margin-left: 6px;
    margin-top: 12px;
    font-size: 14px;
    line-height: 21px;
    font-weight: 500;
}

.wrapper {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: space-evenly;
    margin-top: 24px;
}

.value {
    margin-left: -12px;
}
</style>
  