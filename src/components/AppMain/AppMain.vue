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
                        <div class="img-box">
                            <img src="" alt="">
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
main {
    > div {
        background-color: #d88c3c;
    }
}
#typeList {
    border: none;
    text-decoration: none;
}

.cardsNumber {
    width: 90%;
    height: 50px;
    background-color: black;
    > div {
        color: white;
    }
}

.cardsContainer {
    width: 90%;
    .carta {
        width: calc((100% / 5) - 20px);
        background-color: #d88c3c;
        height: 450px;
    }
}

.img-box {
    width: 100%;
    height: 70%;
    > img {
        width: 100%;
        height: 100%;
    }
}

.text-box {
    width: 100%;
    height: 30%;
}

.select {
    margin-left: 5.9%;
}
</style>
