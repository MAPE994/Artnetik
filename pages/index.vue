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
            <div class="container-left">
                <img src="" alt="wineyard image">
                <h2>{{vineyardId}}</h2>
            </div>
            <div class="container-right">
                <p></p>
            </div>
        </div>
    </div>    
</template>
<script lang="ts">
import wineyardLink from "@/components/Wineyard-link.vue";
import json from '@/json/wineyards.json'

export default {
    components : {
        wineyardLink
    },
    data() {
      return {
        wineyards: json,
        vineyardId: ""
      }
    },
    methods : {
        vineyardSelected : function(event: Object, wineyardId: string) {
            var self = this;
            console.log("haha: ", wineyardId);
            self.vineyardId = wineyardId
            //Vue.set(this.vineyardId, 'id', wineyardId)
        }
    }
}
</script>
<style lang="scss">
    div {
        border: 1px black solid;
    }

    .wineyards,
    .wineyard-details {
        width: 100%;
        display: flex;
        justify-content: space-evenly;
    }

    .wineyards {
        box-shadow: inset 0 -10px 10px -10px #000000;
    }
</style>
