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

    name: "vineyardDetails",
    props: [
        "selectedVineyard"
    ]
}
</script>

<style lang="scss">
    .vineyard-details-container {
        display: flex;
        justify-content: center;    

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

    @media only screen and (max-width: 450px) {
        .vineyard-details-container {
        display: block;

        .container-left {
            margin-top: 50px;
            padding: 0;
            width: 100%;
            max-width: 100%;

            h2 {
               text-align: center; 
            }

            h3 {
                text-align: center;
            }

            svg {
                width: 100%;
                height: 100px;
                fill: #D3A6A3;
            }   
        }
        
        .container-right {
            p {
                text-align: center;
                max-width: 100%;
                margin-top: 0;
            }
        }
    }
    }
</style>