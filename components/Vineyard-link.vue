<template>
    <div class="vineyard-link" v-bind:class="{ active: isActive }">
        <div v-html="image"/>
        <h2>{{ name }}</h2>
    </div>
</template>

<script>
export default {
    name: "vineyardLink",
    props: [
        "name",
        "image",
        "isActive"
    ]
}
</script>

<style lang="scss">
    .vineyard-link {
        margin-top: 100px;
        margin-bottom: 85px;
        cursor: pointer;

        h2 {
            text-align: center;
            font-family: 'Courier Prime Bold';
            font-size: 30px;
            color: #fff;
        }

        svg {
            height: 100px;
            fill: #fff;
        }

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
    }
    .slick-slider {
        .vineyard-link {
            margin-bottom: 0px;

            h2 {
            text-align: center;
            font-family: 'Courier Prime Bold';
            font-size: 30px;
            color: #D3A6A3;
            }

            svg {
                height: 100px;
                width: 100%;
                fill: #D3A6A3;
            }
        }
    } 

    .active {
        svg {
            fill: #D3A6A3;
        }

        h2 {
            color: #D3A6A3;
        }

        &::after {
            position: absolute;
            content: "";
            top: 355px;
            width: 0;
            height: 0;
            border-left: 50px solid transparent;
            border-right: 50px solid transparent;
            border-bottom: 25px solid #fff;
        }

    }
</style>