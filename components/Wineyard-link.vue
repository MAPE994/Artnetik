<template>
    <div class="wineyard-link">
        <div v-html="image"/>
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

<style lang="scss">
    .wineyard-link {
        background-color: burlywood;
        cursor: pointer;

        svg {
            fill: #fff;
            &:hover {
                fill: #D3A6A3;
            }
        }
    }
</style>