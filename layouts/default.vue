<template>
  <v-app>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color="primary"
    >
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      title: '業種UIプレイグラウンド'
    }
  }
}
</script>
