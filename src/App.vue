<template>
  <div id="app">
    <v-app class="grey darken-3">
      <v-navigation-drawer app>
        <!-- -->
      </v-navigation-drawer>

      <v-app-bar app>
        <!-- -->
      </v-app-bar>

      <!-- Sizes your content based upon application components -->
      <v-main>

        <!-- Provides the application the proper gutter -->
        <v-container fluid>
          <a href="/items">Posts</a>
          <a href="/users">Users</a>

          <v-switch
            v-model="lightTheme"
            label="Theme"
          ></v-switch>

          <!-- If using vue-router -->
          <router-view></router-view>
        </v-container>
      </v-main>

      <v-footer app>
        <!-- -->
      </v-footer>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    lightTheme: true
  }),
  watch: {
    lightTheme(isLight) {
      this.$vuetify.theme.dark = !isLight
    }
  }
}
</script>

<style lang="stylus">

</style>
