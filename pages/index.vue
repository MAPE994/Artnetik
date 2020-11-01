<template>
    <div class="wineyards-container">
        <div class="wineyards">
            <wineyardLink v-for = "wineyard in wineyards"
                        v-bind:key = "wineyard.id"
                        v-bind:image = "wineyard.image"
                        v-bind:name = "wineyard.name"
                        v-bind:isActive = "wineyard.isActive"
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
    components: {
        wineyardLink,
        vineyardDetails
    },
    data() {
      return {
        wineyards: json,
        selectedVineyard: Object,
      }
    },
    methods : {
        vineyardSelected: function(event: Object, wineyardId: String) {
            var self = this;
            
            self.wineyards.forEach((vineyard: Object) => {
                if (vineyard.id === wineyardId) {
                    vineyard.isActive = true;
                    self.selectedVineyard = vineyard
                } else {
                    vineyard.isActive = false;
                }
            });
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
        box-shadow: inset 0 -200px 200px -160px #606060 
    }
</style>
