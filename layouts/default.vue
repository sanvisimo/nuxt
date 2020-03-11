<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar :clipped-left="clipped" fixed app color="white" height="75">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <div class="d-flex justify-center align-center" style="width: 100%;">
        <div class="d-inline-block">
          <img alt="Medboat" src="/logo.png" />
        </div>
      </div>
    </v-app-bar>

    <v-content>
      <v-container class="d-flex align-center" style="min-height: calc(100vh - 131px)">
        <nuxt />
      </v-container>
    </v-content>

    <v-footer
      :fixed="fixed"
      app
      color="primary"
      class="white--text text-center"
    >
      <div class="copyright">
        &copy; {{ new Date().getFullYear() }} info@medboatsharing.com - 5 UP srl
        - P. IVA 02329330977
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data(to = "/") {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: to
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire"
        },
        {
          icon: "mdi-new-box",
          title: "Nuova",
          to: "/nuova"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "MEdboat"
    };
  }
};
</script>

<style lang="scss">
.copyright {
  width: 100%;
  position: relative;
  font-size: 85%;
  letter-spacing: 1px;
  padding: 12px 0;
}
</style>
