<template>
    <div class="wineyards-container">
        <div class="wineyards">
            <wineyardLink v-for = "wineyard in wineyards"
                        v-bind:key = "wineyard.id"
                        v-bind:image = "wineyard.image"
                        v-bind:name = "wineyard.name"
                        v-on:click.native = "vineyardSelected($event, wineyard.id)"            
            />
        </div>
        <div class="wineyard-details">
            <vineyardDetails
                v-bind:selectedVineyard = "selectedVineyard"
            />
        </div>
    </div>    
</template>
<script lang="ts">
import wineyardLink from "@/components/Wineyard-link.vue";
import vineyardDetails from "@/components/Vineyard-details.vue";
import json from '@/json/wineyards.json'

export default {
    components : {
        wineyardLink,
        vineyardDetails
    },
    data() {
      return {
        wineyards: json,
        selectedVineyard: "",
      }
    },
    methods : {
        vineyardSelected : function(event: Object, wineyardId: String) {
            var self = this;
            self.wineyards.forEach(function(vineyard: Object){
                if (vineyard.id === wineyardId) {
                    self.selectedVineyard = vineyard
                }
            })
        }
    }
}
</script>
<style lang="scss">

    .wineyards,
    .wineyard-details {
        width: 100%;
        display: flex;
        justify-content: space-evenly;
    }

    .wineyards {
        box-shadow: inset 0 -100px 100px -80px #000000 
    }
</style>
