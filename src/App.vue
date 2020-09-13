<template>
  <v-app>
    <v-app-bar app color="grey lighten-4" flat light>
      <v-btn fab small light @click.stop="drawer = !drawer" class="mx-2">
        <v-icon dark>mdi-dots-vertical</v-icon>
      </v-btn>
      <v-toolbar-title class="mx-2">Admin Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn text>
          <v-icon>mdi-cog</v-icon>
        </v-btn>
        <v-btn text>
          <v-icon>mdi-logout</v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

    <v-navigation-drawer
      style="background-image: linear-gradient(to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5));"
      v-model="drawer"
      src="https://images.unsplash.com/photo-1512514076443-1eef59c260b0?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=675&q=80"
      dark
      app
    >
      <v-list nav class="py-0">
        <v-list-item>
          <v-list-item-avatar size="72">
            <img
              src="https://portal.venturedevelopment.institute/images/20200507logo.svg"
            />
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Startup Online</v-list-item-title>
            <v-list-item-subtitle>Admin Dashboard</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item link class="my-2">
          <v-list-item-icon>
            <v-icon>mdi-view-dashboard-outline</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link class="my-2 active">
          <v-list-item-icon>
            <v-icon>mdi-book-open-variant</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Course Details</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link class="my-2">
          <v-list-item-icon>
            <v-icon>mdi-account-group</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Customer Details</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main class="grey lighten-4">
      <v-container>
        <v-data-table
          :headers="headers"
          :items="desserts"
          :items-per-page="5"
          class="elevation-1 my-6"
        ></v-data-table>
      </v-container>
    </v-main>
    <v-footer class="font-weight-medium grey lighten-5">
      <v-col class="d-flex justify-end" cols="12">
        {{ new Date().getFullYear() }} —
        <strong>Venture Development Institite</strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    drawer: null,
    headers: [
      {
        text: "Dessert (100g serving)",
        align: "start",
        sortable: false,
        value: "name",
        class: "black--text"
      },
      { text: "Calories", value: "calories", class: "black--text" },
      { text: "Fat (g)", value: "fat", class: "black--text" },
      { text: "Carbs (g)", value: "carbs", class: "black--text" },
      { text: "Protein (g)", value: "protein", class: "black--text" },
      { text: "Iron (%)", value: "iron", class: "black--text" }
    ],
    desserts: [
      {
        name: "Frozen Yogurt",
        calories: 159,
        fat: 6.0,
        carbs: 24,
        protein: 4.0,
        iron: "1%"
      },
      {
        name: "Ice cream sandwich",
        calories: 237,
        fat: 9.0,
        carbs: 37,
        protein: 4.3,
        iron: "1%"
      },
      {
        name: "Eclair",
        calories: 262,
        fat: 16.0,
        carbs: 23,
        protein: 6.0,
        iron: "7%"
      },
      {
        name: "Cupcake",
        calories: 305,
        fat: 3.7,
        carbs: 67,
        protein: 4.3,
        iron: "8%"
      },
      {
        name: "Gingerbread",
        calories: 356,
        fat: 16.0,
        carbs: 49,
        protein: 3.9,
        iron: "16%"
      },
      {
        name: "Jelly bean",
        calories: 375,
        fat: 0.0,
        carbs: 94,
        protein: 0.0,
        iron: "0%"
      },
      {
        name: "Lollipop",
        calories: 392,
        fat: 0.2,
        carbs: 98,
        protein: 0,
        iron: "2%"
      },
      {
        name: "Honeycomb",
        calories: 408,
        fat: 3.2,
        carbs: 87,
        protein: 6.5,
        iron: "45%"
      },
      {
        name: "Donut",
        calories: 452,
        fat: 25.0,
        carbs: 51,
        protein: 4.9,
        iron: "22%"
      },
      {
        name: "KitKat",
        calories: 518,
        fat: 26.0,
        carbs: 65,
        protein: 7,
        iron: "6%"
      }
    ]
  })
};
</script>

<style scoped>
.active {
  background-color: #673ab7 !important;
}
</style>
