<template>
  <v-app>
    <v-content>
      <v-container>
        <Header />
        <nuxt />
      </v-container>
    </v-content>
    
    
  </v-app>
</template>

<script>
import Header from '@/components/Header'
  export default {
    components:{
      Header
    },
    data() {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Welcome', to: '/' },
          { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
