<template>
  <v-toolbar>
    <v-toolbar-side-icon @click="toMainPage()"></v-toolbar-side-icon>
    <v-toolbar-title>Visual Explain</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat @click="openMyGithub()">
        <v-avatar size="42">
          <img
            src="https://img.freepik.com/vector-gratis/avatar-personaje-empresario-aislado_24877-60111.jpg?size=338&ext=jpg"
          />
        </v-avatar>
        <span style="margin-left: 8px">About me: ssthouse</span>
      </v-btn>
      <v-tooltip bottom>
        <v-btn slot="activator" flat :href="sourceCodeLink">
          <v-avatar size="42">
            <img
              src="https://img.freepik.com/vector-gratis/avatar-personaje-empresario-aislado_24877-60111.jpg?size=338&ext=jpg"
            />
          </v-avatar>
          Source Code
        </v-btn>
        <span class="top-bar-tooltip"
          >Welcome to fork & star <br />
          ; )</span
        >
      </v-tooltip>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'PalaceTitleBar', // vue component name
  props: ["sourceCodeLink"],
  methods: {
    openMyGithub() {
      const a = document.createElement("a");
      a.target = "_blank";
      a.href = "https://github.com/crisanto-lopez-gonet";
      a.click();
    },
    toMainPage() {
      this.$emit("to-main-page");
    },
  },
});
</script>

<style scoped>
.top-bar-tooltip {
  font-size: 18px;
}

a {
  color: black;
}
</style>
