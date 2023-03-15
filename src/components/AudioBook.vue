<script>

export default {
    data() {
        return {
            images: [
                '/src/image/ebay-logotan-2x-600x197.png',
                '/src/image/audible-logotan-2x-600x197.png',
                '/src/image/bb-logotan-2x-600x197.png',
                '/src/image/kindlefire-logotan-2x-600x197.png'
            ],
            colorImages: [
                '/src/image/audible-logo.png',
                '/src/image/bn-logo-tall.png',
                '/src/image/kindle-logo-tall.png',
            ]
        }
    }
}


</script>

<template>

    <section class="rose">
        <div class="container-sm">
            <ul class="mb-0 images">
                <li v-for="image in images" :key="image">
                    <img :src="image" alt="">
                </li>
            </ul>
        </div>
    </section>

    
    <section class="bg-space">
        <div class="container-sm">
            <div class="row text-light">
                <div class="image-phone mt-md-0 mt-sm-5 col-xl-5 col-md-12 order-xl-first order-md-last order-sm-last">
                    <img src="/src/image/audible-app-2x-800x837.png" alt="">
                </div>
                <div class="text col-xl-5 col-md-12">
                    <h3>
                        New Audiobook
                    </h3>
                    <p class="yellow">
                        NO TIME TO READ? NO PROBLEM. LISTEN TO IT
                    </p>
                    <p class="subtitle">
                        Donec fringilla nunc eu turpis dignissim, at euismod sapien tincidunt. Maecenas eleifend congue cursus.
                    </p>
                    <ul class="color-images p-0 d-xl-flex d-md-none d-sm-none">
                        <li v-for="image in colorImages">
                            <img :src="image" alt="">
                        </li>
                    </ul>
                    <button class="w-25 text-light d-xl-none d-md-block d-sm-block">
                        <i class="fa-brands fa-audible"></i>
                        Buy This On Audible
                    </button>
                </div>
            </div>
        </div>
        
    </section>

</template>

<style lang="scss" scoped>

@use '/src/style/partials/_variables.scss' as *;

.rose {
    background-color: $rose;

    ul.images {
        display: flex;
        padding: 60px 0;
        gap: 50px;

        & > *:hover {
            cursor: pointer;
        }
    }
}

.bg-space {
    background-image: url(/src/image/banner.jpg);
    background-size: cover;
    background-position: center;
    padding-top: 70px;

    .row {
        align-items: center;
        text-align: center;
        justify-content: space-between;

        .image-phone {
            min-width: 500px;
        }

        .text {
            display: flex;
            flex-direction: column;
            align-items: center;

            h3, .yellow {
                font-family: $family-playfair;
            }

            h3 {
                font-size: 40px;
                margin-bottom: 10px;
            }

            .yellow {
                color: $yellow;
                font-size: 18px;
            }

            .subtitle {
                color: rgba( #ffffff, 0.6);
            }

            ul.color-images {
                display: flex;
                gap: 20px;
                justify-content: center;
            }

            button {
                line-height: 42px;
                min-width: 220px;
                border: 0;
                background-color: $green;
                border-radius: 5px;
                margin: 30px 0;
                transition: 0.2s;

                i {
                    padding-right: 5px;
                }

                &:hover {
                    background-color: $dark-green;
                    transition: 0.2s;
                }
            }
        }
    }
}

@media (max-width: 1200px) {
    .text {
        padding: 0 20%;
        margin-bottom: 20px;
    }

    .row {
        justify-content: center !important;
    }

    .image-phone{
        width: 35%;
    }
}

</style>
