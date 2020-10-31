<template>
<div class="vineyard-details-container">
    <div class="container-left">
        <div v-html="selectedVineyard.image"/>
        <h2>{{selectedVineyard.name}}</h2>
        <h3>{{selectedVineyard.description}}</h3>
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
    @font-face {
        font-family: 'Courier Prime Bold';
        font-style: normal;
        font-weight: 400;
        font-display: swap;
        src: url('~assets/fonts/CourierPrime-Bold.ttf') format('truetype');
    }

    @font-face {
        font-family: 'Courier Prime Regular';
        font-style: normal;
        font-weight: 200;
        font-display: swap;
        src: url('~assets/fonts/CourierPrime-Regular.ttf') format('truetype');
    }

    .vineyard-details-container {
        display: flex;
        align-items: center;
        
        .container-left {
            padding: 70px;
            width: 30%;
            max-width: 30%;
            h2 {
                font-family: 'Courier Prime Bold';
                font-size: 42px;
                color: #221F20;
            }
            h3 {
                font-family: 'Courier Prime Bold';
                font-size: 22px;
                color: #D3A6A3;
            }
            svg {
                height: 100px;
                fill: #D3A6A3;
            }   
        }
        .container-right {
            p {
                font-family: 'Courier Prime Regular';
                font-size: 18px;
                max-width: 560px;
                margin-top: 270px;
            }
        }
    }
</style>