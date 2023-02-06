<script>
  import AppHeader from "./components/AppHeader/AppHeader.vue"
  import AppMain from "./components/AppMain/AppMain.vue"
  import AppFooter from "./components/AppFooter/AppFooter.vue"
 
  export default { 

  data () {
      return { 
          
      }

  },
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  created() {
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Blue-Eyes')
    .then((response) => {
      console.log (response)
    }

  )}
  }
</script>


<template>
  <AppHeader />
  <AppMain />
  <AppFooter />
</template>

<style lang="scss"> 
@import './styles/main';
</style>
