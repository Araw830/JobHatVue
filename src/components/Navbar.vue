<template>
<nav>
  <v-app-bar flat app class="black">
     <v-app-bar-nav-icon class="white--text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
          <span class="font-weight-light">Job</span>
           <span class="font-weight-dark">Hat</span>
      </v-toolbar-title>

       <v-toolbar-title class="text-uppercase grey--text ml-10" >
         
        
      <v-row justify="center">

    <v-dialog v-model="dialog" persistent max-width="600px">
      <template v-slot:activator="{ on }">
        <v-card-text flat class="ml-10 hidden-xs-only" color="primary" dark v-on="on">Find Job</v-card-text>
      </template>
      <v-card>
        <v-card-title>
          <span class="headline">User Profile</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-text-field label="Legal first name*" required></v-text-field>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field label="Legal middle name" hint="example of helper text only on focus"></v-text-field>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  label="Legal last name*"
                  hint="example of persistent helper text"
                  persistent-hint
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Email*" required></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Password*" type="password" required></v-text-field>
              </v-col>
              <v-col cols="12" sm="6">
                <v-select
                  :items="['0-17', '18-29', '30-54', '54+']"
                  label="Age*"
                  required
                ></v-select>
              </v-col>
              <v-col cols="12" sm="6">
                <v-autocomplete
                  :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                  label="Interests"
                  multiple
                ></v-autocomplete>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
          <v-btn color="blue darken-1" text @click="dialog = false">Save</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
          
      </v-toolbar-title>

        <!-- <v-toolbar-title class="text-uppercase grey--text ml-10" >
          <span class="font-weight-light ml-10">Find Salaries</span>
          </v-toolbar-title> -->
           <v-spacer></v-spacer>
       
     


  
      
    

       <v-spacer></v-spacer><span class="white--text">Logout</span>
       <v-btn icon>
        <v-icon class="white--text">mdi-export</v-icon>
      </v-btn>
     
   
       
  </v-app-bar>
   <v-navigation-drawer
        v-model="drawer"
        app
        collapse="true"
        
        
       
      
        
         src="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
      >
        <v-list-item>
          <v-list-item-avatar>
            <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
          </v-list-item-avatar>
  
          <v-list-item-content>
            <v-list-item-title class="white--text">Atul Rawat</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
  
        <v-divider></v-divider>
  
        <v-list dense>
  
          <v-list-item
          class="iten"
          
            v-for="item in items"
            :key="item.title"
            link
            router :to="item.route"
            
          >
            <v-list-item-icon>
              <v-icon class=" hidden-sm-and-up" v-if="item.title === 'Find Job'">{{ item.icon }}</v-icon>
              <v-icon class="" v-else-if="item.title !== 'Find Job'">{{ item.icon }}</v-icon>
            </v-list-item-icon>
  
            <v-list-item-content>
         
              <v-list-item-title class="white--text hidden-sm-and-up" v-if="item.title === 'Find Job'" @click.stop="dialog = true">{{ item.title }}</v-list-item-title>
             
              <v-list-item-title class="white--text " v-else-if="item.title !== 'Find Job'">{{ item.title }}</v-list-item-title>

            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
</nav>
    
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

<style scoped>
.item{
     margin-left: 0.2rem;
}

.ml-10{
  margin-left: ($spacer-x * .25) !important;
}


</style>