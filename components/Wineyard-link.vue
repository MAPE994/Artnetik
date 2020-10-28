<template>
    <div class="wineyard-link">
        <img :src="image" alt="wineyard image">
        <h2>{{ name }}</h2>
    </div>
</template>
<script>
export default {
    name : "wineyardLink",
    props: [
        "name",
        "image"
    ]
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