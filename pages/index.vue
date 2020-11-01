<template>
    <div class="vineyards-container">
        <div class="vineyards">
            <vineyardLink v-for = "vineyard in vineyards"
                        v-bind:key = "vineyard.id"
                        v-bind:image = "vineyard.image"
                        v-bind:name = "vineyard.name"
                        v-bind:isActive = "vineyard.isActive"
                        v-on:click.native = "vineyardSelected($event, vineyard.id)"            
            />
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
import json from '@/json/vineyards.json';

export default {
    components: {
        vineyardLink,
        vineyardDetails
    },
    data() {
      return {
        vineyards: json,
        selectedVineyard: json[0],
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
        box-shadow: inset 0 -200px 200px -160px #606060 
    }
</style>
