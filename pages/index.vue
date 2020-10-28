<template>
    <div class="wineyards-container">
        <div class="wineyards">
            <wineyardLink v-for = "wineyard in wineyards"
                      v-bind:key = "wineyard.id"
                      v-bind:image = "wineyard.image"
                      v-bind:name = "wineyard.name"
            />
        </div>
        <div class="wineyard-details">
            <div class="container-left">
                <img src="" alt="wineyard image">
                <h2></h2>
            </div>
            <div class="container-right">
                <p></p>
            </div>
        </div>
    </div>    
</template>
<script>
import wineyardLink from "@/components/Wineyard-link.vue";
import json from '@/json/wineyards.json'

export default {
    components : {
        wineyardLink
    },
    data() {
      return {
        wineyards: json
      }
    }
}
</script>
<style>
    div {
        border: 1px black solid;
    }

    .wineyards-container,
    .wineyard-details {
        width: 100%;
    }

    .wineyard-details {
        display: flex;
    }
</style>
