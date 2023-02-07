<script>
import axios from 'axios';

export default {
    name: 'AppMain',
    props: {
        archetypeList: {
            type: Array,
            default: []
        },
        
    },
    data () {
        return {
            msg: 'Ciao',
            count: 0,
            archeDetails: [],
            archetypeSelected: ''
        }

    },
    created () {
        
    },
    methods: {
        updateCardsWith(archetype) {     

                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${archetype}`)
                  .then((response) => {
                    this.archeDetails = response.data.data
                    console.log('archeDetails', this.archeDetails)
              })
                
        }
    }
};
</script>

<template>
    <main>
        <!-- Container principale con background marrone  -->
        <div class="container-fluid pb-5">

            <!-- Select options -->
            <div class="container mx-auto">
                <div class="select py-4 container d-flex gx-0">
                    <select v-model="archetypeSelected" @change="updateCardsWith(archetypeSelected)" class="" name="typeList" id="typeList">
                        <option v-for="element in archetypeList" :value="element.archetype_name">
                            {{ element.archetype_name }}
                        </option>
                    </select>
                </div>
            </div>

            <!-- Container centrale con sfondo bianco -->
            <div class="container mx-auto bg-light py-5">

                <!-- Barra nera con numeri di elementi trovati nell'API -->
               <div class="cardsNumber d-flex justify-content-start align-items-center ps-2 mx-auto">
                    <div>
                     Found {{ archeDetails.length }} cards
                    </div>
               </div>

               <!-- Contenitore delle cards -->
               <div class="cardsContainer mx-auto d-flex justify-content-between flex-wrap">
                <!-- Struttura della carta specifica:  -->
                    <div v-for="monster in archeDetails" class="carta mb-3">
                        <!-- Immagine carta  -->
                        <div v-for="element in monster.card_images" class="img-box">
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
