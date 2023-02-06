<script>
export default {
    name: 'AppHeader',
    data () {
        return {
            msg: 'Ciao',
            count: 0,
        }

    }
};
</script>

<template>
    <header>
        <div>
            <!-- Logo Yu-gi-ho  -->
            <div class="logo ps-4">
              <img class="img-fluid" src="http://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="">
             </div>

             <!-- Scritta Yu-gi-ho  -->
             <div class="container-fluid">
                 Yu-Gi-ho Api
             </div>
        </div>
    </header>
</template>

<style lang="scss">
@import '../../styles/partials/HeaderAttributes/HeaderAttributes.scss';
</style>
