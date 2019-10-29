<template>
  <div>
    <v-toolbar>
      <v-toolbar-title style="color:lightgrey;">portfolio</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn class="header-item" to="/" nuxt>トップへ</v-btn>
        <v-btn class="header-item" to="/works" nuxt>作成実績</v-btn>
      </v-toolbar-items>
    </v-toolbar>
  </div>
</template>

<style>
.header-item{
  background-color: rgba(0, 0, 0, 0.87);
}
</style>