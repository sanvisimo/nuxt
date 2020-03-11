<template>
  <v-container align-self="center">
    <v-row justify="space-around" align="stretch">
      <v-col
        cols="4"
        class="d-flex justify-center align-center choice"
        v-for="(el, i) in elements"
        :key="i"
      >
        <v-btn color="primary" tile>{{ el.desc }}</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data: function() {
    return {
      elements: [
        {
          type: "boat",
          name: "barca",
          desc: this.$i18n.t("home.boat")
        },
        {
          type: "harbour",
          name: "barca",
          desc: this.$i18n.t("home.harbour")
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.choice {
  border: 1px solid #000;
}
</style>
