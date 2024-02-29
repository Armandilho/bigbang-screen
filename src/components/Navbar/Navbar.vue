<template>
  <v-container fluid class="header">
    <v-toolbar app color="transparent">
      <v-row justify="space-between" align="center">
        <v-col class="hidden-md-and-up">
          <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer" color="#FFF" />
        </v-col>
        <v-col cols="auto">
          <v-toolbar-title>
            <router-link to="/" tag="span" style="cursor: pointer">
              <v-img width="90" height="23" src="@/assets/logo.svg" />
            </router-link>
          </v-toolbar-title>
        </v-col>
        <v-col cols="auto hidden-sm-and-down">
          <v-toolbar-items flat>
            <v-btn flat v-for="item in menuItems" :key="item.title"
              :color="item.title === 'Dashboard' ? '#FF6969' : '#FFF'" height="40px" max-width="140px" class="mx-2"
              :variant="item.title === 'Dashboard' ? 'flat' : 'text'">
              {{ item.title }}
            </v-btn>
          </v-toolbar-items>
        </v-col>
        <v-col cols="auto">
          <v-icon icon="fa-regular fa-bell" color="#FFF" size="small" />
        </v-col>
      </v-row>
    </v-toolbar>
  </v-container>
</template>
  
<script>

export default {
  name: "Navbar",
  data() {
    return {
      sidebar: false,
      menuItems: [
        { title: 'Dashboard', path: '/Dashboard' },
        { title: 'Pagamentos', path: '/Pagamentos' },
        { title: 'Invoices', path: '/Invoices' },
        { title: 'Insights', path: '/Insights' }
      ]
    }
  },
};

</script>
<style>
.header {
  padding: 0;
  width: 100%;
  background: transparent;
}
</style>
  