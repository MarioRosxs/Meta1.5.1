<template>
  <v-navigation-drawer app permanent width="250">
    <!-- Contenido del menú -->
    <v-list>
      <v-list-item
        prepend-avatar="~@/assets/avatar.png"
        title="Mario Rosas"
        subtitle="mrosas60@uabc.edu.mx"
      ></v-list-item>
    </v-list>

    <v-divider></v-divider>

    <v-list dense nav>
      <v-list-item
        v-for="item in menuItems"
        :key="item.title"
        :prepend-icon="item.icon"
        :title="item.title"
        @click="navigateTo(item.route)"
      ></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      menuItems: [
        { title: "Principal", icon: "mdi-home", route: "home" },
        { title: "Tabla", icon: "mdi-table", route: "tabla" },
        { title: "Imagen", icon: "mdi-image", route: "imagen" },
      ],
    };
  },
  methods: {
    navigateTo(routeName) {
      // Redirige al usuario a la página correspondiente
      this.$router.push(routeName);
    },
  },
};
</script>
