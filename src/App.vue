<script>
  import AppHeader from "./components/AppHeader/AppHeader.vue"
  import AppMain from "./components/AppMain/AppMain.vue"
  import AppFooter from "./components/AppFooter/AppFooter.vue"
  import axios from 'axios'
 
  export default { 

  data () {
      return { 
          monsters: [],
      }

  },
  components: {
    AppHeader,
    AppMain,
    AppFooter,
  },
  created() {
    
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype="Blue-Eyes"')
    .then((response) => {
      console.log(response.data)
      this.monsters = response.data.data
      console.log(this.monsters)
    }

  )}
  }
</script>


<template>
  <AppHeader />

  <AppMain :monsterList="monsters" />

  <AppFooter />
</template>

<style lang="scss"> 
@import './styles/main';
</style>
