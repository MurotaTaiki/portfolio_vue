<template>
  <v-app>
    <TheHeader />
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import TheHeader from '~/components/TheHeader.vue'

export default{
  components: {
    TheHeader
  }
}

</script>