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
        margin-top: 100px;
        cursor: pointer;
        &:hover {
            h2 {
                transition-duration: 0.1s;
                color: #D3A6A3;
            }
            svg {
                transition-duration: 0.3s;
                fill: #D3A6A3;
            }
        }

        h2 {
            font-family: 'Courier Prime Bold';
            font-size: 30px;
            color: #fff;
        }

        svg {
            height: 100px;
            fill: #fff;
        }
    }
</style>