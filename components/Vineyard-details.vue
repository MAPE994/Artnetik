<template>
<div class="vineyard-details-container">
    <div class="container-left">
        <div v-html="selectedVineyard.image"/>
        <h2>{{selectedVineyard.name}}</h2>
        <h3>{{selectedVineyard.descripotion}}</h3>
    </div>
    <div class="container-right">
        <p>{{selectedVineyard.text}}</p>
    </div>
</div>
</template>
<script>
export default {

    name : "vineyardDetails",
    props: [
        "selectedVineyard"
    ]
}
</script>

<style lang="scss">
svg {
        fill: #D3A6A3;
    }
</style>