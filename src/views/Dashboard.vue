<template>
  <v-card
  
  
    class="mx-auto mt-7"
    width="1200"
    ripple
    outlined
    shaped
    
    
  >
    <v-list-item three-line >
      <v-list-item-content>
        <div class="overline mb-4">JobsHat</div>
        <v-list-item-title class="headline mb-1">Amazon Web Service Software Developer</v-list-item-title>
        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
      </v-list-item-content>
 <v-avatar>
      <img
        src="https://cdn.vuetifyjs.com/images/john.jpg"
        alt="John"
      >
    </v-avatar>
    </v-list-item>

    <v-card-actions>
        <v-btn icon>
                <v-icon>mdi-heart</v-icon>
              </v-btn>
      <v-btn icon>
        
                <v-icon>mdi-bookmark</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>mdi-share-variant</v-icon>
              </v-btn>
    </v-card-actions>
  </v-card>
  
</template>
<script>
export default {
    data(){
        return{
          dialog:false,
            drawer: false,
             items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard',route:'/' },
        { title: 'Home', icon: 'mdi-home',route:'/home' },
        { title: 'About', icon: 'mdi-account',route:'/about' },
          { title: 'Find Job', icon: 'mdi-account' },
      ],
       right: null,
        }
    }
    
}


</script>

<style  scoped>


</style>