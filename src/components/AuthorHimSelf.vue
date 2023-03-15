<script>
    export default {
        data() {
            return {
                cards: [
                    {
                        image: '/src/image/box-1.jpg',
                        title: 'About Me',
                        text: 'Vestibulum ante ipsum primis',
                    },
                    {
                        image: '/src/image/box-4.jpg',
                        title: 'My Latest Book',
                        text: 'Vestibulum ante ipsum primis',
                    },
                    {
                        image: '/src/image/box-3.jpg',
                        title: 'Book Signing',
                        text: 'Vestibulum ante ipsum primis',
                    },
                ]
            }
        }
    }

</script>

<template>
    <section>
        <div class="container text-center">
            <h2>
                Dig A Little Deeper Into Damon Vaughn
            </h2>
            <p class="green mb-0">
                FIND OUT MORE ABOUT THE AUTHOR HIMSELF
            </p>
            <div class="grid">
                <div v-for="card in cards" class="card text-bg-dark">
                    <img :src="card.image" alt="">
                    <div class="card-img-overlay">
                        <div class="text">
                            <h5 class="card-title">
                                {{ card.title }}
                            </h5>
                            <p class="card-text">
                                {{ card.text }}
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    

</template>

<style lang="scss" scoped>

    @use '/src/style/partials/_variables.scss' as *;

    .container {
        padding: 80px 0 60px 0;

        h2 {
            font-family: $family-playfair;
            font-weight: 600;
            font-size: 40px;
        }

        p.green {
            color: $green;
            font-size: 18px;
            font-weight: 400;
            padding: 15px 0 60px 0;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            column-gap: 50px;
            padding: 0 12%;

            .card {
                border: 0;
                

                &:hover img {
                    transition: 0.7s;
                    transform: scale(1.05);
                    filter: drop-shadow(5px 5px 6px rgb(94, 86, 86));
                }
                
                &, img {
                    border-radius: 0 0 40px 0;

                    img {
                        height: 520px;
                        object-fit: cover;
                        object-position: left;
                        transition: 0.5s;
                        transform: scale(1);
                    }
                }

                .card-img-overlay {
                    display: flex;
                    flex-direction: column;
                    justify-content: flex-end;
                    align-items: center;
                    padding: 25px;

                    .card-title {
                        font-size: 30px;

                        &::after {
                            content: '';
                            display: block;
                            width: 50%;
                            height: 1px;
                            background-color: rgba( #ffffff, 0.4);
                            margin: 20px auto;
                        }
                    }
                    .card-text {
                        color: $yellow;
                        font-size: 20px;
                        font-weight: 500;
                    }
                }
            }
        }
    }

</style>