<template>
    <div class="vineyards-container">
        <div class="vineyards" v-if="$mq !== 'sm'" :style="{ backgroundImage: `url(${bgImage})`}">
            <vineyardLink v-for = "vineyard in vineyards"
                        v-bind:key = "vineyard.id"
                        v-bind:image = "vineyard.image"
                        v-bind:name = "vineyard.name"
                        v-bind:isActive = "vineyard.isActive"
                        v-on:click.native = "vineyardSelected($event, vineyard.id)"            
            />
        </div>
        <div class="carousel-mobile" v-if="$mq === 'sm'" :style="{ backgroundImage: `url(${bgImage})`}">
            <vueSlickCarousel :dots="true">
                    <vineyardLink v-for = "vineyard in vineyards"
                        v-bind:key = "vineyard.id"
                        v-bind:image = "vineyard.image"
                        v-bind:name = "vineyard.name"
                        v-bind:isActive = "vineyard.isActive"
                        v-on:click.native = "vineyardSelected($event, vineyard.id)"            
                    />
            </vueSlickCarousel>  
        </div>
        <div class="vineyard-details">
            <vineyardDetails
                v-bind:selectedVineyard = "selectedVineyard"
            />
        </div>
    </div>    
</template>

<script>
import vineyardLink from "@/components/Vineyard-link.vue";
import vineyardDetails from "@/components/Vineyard-details.vue";
import vueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import bgImage from "assets/img/vinograd.jpg";
import json from '@/json/vineyards.json';

export default {
    components: {
        vineyardLink,
        vineyardDetails,
        vueSlickCarousel
    },
    data() {
      return {
        bgImage: bgImage,  
        vineyards: json,
        selectedVineyard: json[0],
      }
    },
    head() {
        return {
            title: "Artnetik test",
            meta: [
                {
                    hid: 'Artnetik test',
                    name: 'Artnetik test',
                    content: 'Artnetik test'
                }
            ]
        }
    },
    methods : {
        vineyardSelected: function(event, vineyardId) {            
            this.vineyards.forEach((vineyard) => {
                if (vineyard.id === vineyardId) {
                    vineyard.isActive = true;
                    this.selectedVineyard = vineyard
                } else {
                    vineyard.isActive = false;
                }
            });
        }
    }
}
</script>

<style lang="scss">
    .vineyards,
    .vineyard-details {
        width: 100%;
        display: flex;
        justify-content: space-evenly;
    }

    .vineyards {
        box-shadow: inset 0 -200px 200px -160px #606060;
        background-position: center;
    }

    .carousel-mobile {
        background-size: contain;
    }
</style>
