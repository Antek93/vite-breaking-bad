<script>
export default {
    name: 'AppMain',
    props: {
        monsterList: {
            type: Array,
            default: []
        }
    },
    data () {
        return {
            msg: 'Ciao',
            count: 0,
        }

    }
};
</script>

<template>
    <main>
        <!-- Container principale con background marrone  -->
        <div class="container-fluid">

            <!-- Select options -->
            <div class="select py-4">
                <select name="typeList" id="typeList">
                    <option value="Alien">Alien</option>
                    <option value="Monster">Monster</option>
                    <option value="Fairy">Fairy</option>
                </select>
            </div>

            <!-- Container centrale con sfondo bianco -->
            <div class="container mx-auto bg-light py-5">

                <!-- Barra nera con numeri di elementi trovati nell'API -->
               <div class="cardsNumber d-flex justify-content-start align-items-center ps-2 mx-auto">
                    <div>
                     Found {{ monsterList.length }} cards
                    </div>
               </div>

               <!-- Contenitore delle cards -->
               <div class="cardsContainer mx-auto d-flex justify-content-between flex-wrap">
                <!-- Struttura della carta specifica:  -->
                    <div v-for="monster in monsterList" class="carta mb-3">
                        <!-- Immagine carta  -->
                        <div v-for="element in monster.card_images.slice(0,1)" class="img-box">
                            <img :src="element.image_url" alt="">
                        </div>
                        <!-- Nome carta + specie -->
                        <div class="text-box d-flex-column text-center py-2">
                            <div class="py-4 text-light text-xl-center fw-bold">
                                {{ monster.name }}
                            </div>
                            <div class="psy-2">
                                {{ monster.type }}
                            </div>
                        </div>
                    </div>
               </div>

            </div>
        </div>
    </main>
</template>

<style lang="scss">
@import '../../styles/partials/MainAttributes/mainAttributes.scss'
</style>
