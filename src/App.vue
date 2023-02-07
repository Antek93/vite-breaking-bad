<script>
  import AppHeader from "./components/AppHeader/AppHeader.vue"
  import AppMain from "./components/AppMain/AppMain.vue"
  import AppFooter from "./components/AppFooter/AppFooter.vue"
  import axios from 'axios'
 
  export default { 

    data () {
        return { 
            archetypeList: [],
            
        }

    },
    components: {
      AppHeader,
      AppMain,
      AppFooter,
    },
    methods : {
      
    },
    created () {
      
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
          .then((response) => {
              this.archetypeList = response.data
              
      })
          
    }
  }

  
</script>


<template>
  <AppHeader />

  <AppMain
  :archetypeList="archetypeList"
  />

  <AppFooter />
</template>

<style lang="scss"> 
@import './styles/main';
</style>
