<script>

export default {
    data() {
        return {
            authors: [
                {
                    name: 'Gerald Hendley',
                    subname: 'The Guardian',
                    title: 'A True Masterpiece, Bravo!',
                    text: 'Nulla quis lorem ut libero malesuada feugiat. Vivamus magna justo, lacinia eget consectetur sed, convallis at tellus. Vivamus suscipit tortor eget felis porttitor volutpat. Nulla quis lorem ut libero malesuada feug at.',
                    image: '/src/image/theguardian-xsmall.png',
                },
                {
                    name: '	Mary Maxey',
                    subname: 'The Globe And Mail',
                    title: 'A Unique View On The World',
                    text: 'Donec sollicitudin molestie malesuada. Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem. Vestibulum ac diam sit amet quam vehicula elementum sed sit amet dui. Nulla quis lorem ut libero malesuada feugiat. Vestibulum ac diam sit amet.',
                    image: '/src/image/globe-xsmall.png',
                },
            ]
        }
    }
}

</script>

<template>
    <section>
        <div class="container">
            <div class="row">
                <div class="col-auto">
                    <h3>
                        What The Critics Say
                    </h3>
                    <p class="green">
                        TESTIMONIALS FROM AROUND THE WORLD
                    </p>
                </div>
                <div class="col-xl-auto col-md-12 col-sm-12 d-flex flex-column justify-content-center">
                    <button>
                        Read All Testimonials
                    </button>
                </div>
            </div>
            <div class="row">
                <div class="col-xl-7 col-md-12 col-sm-12 best-author">
                    <div class="card text-light">
                        <img src="/src/image/testimonial2-2x.jpg" class="big-image" alt="">
                        <div class="card-img-overlay">
                            <div class=" text-light">
                                <h2>
                                    Best Author Of His Generation
                                </h2>
                                <p>
                                    This book will change yuor prspective on life
                                </p>
                                <p>
                                    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae iure aut sequi necessitatibus velit pariatur perferendis, reiciendis ea praesentium quidem perspiciatis possimus maxime, aspernatur fugit!
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente porro quos atque perferendis tempora consectetur incidunt unde distinctio suscipit voluptatum, rerum obcaecati amet mollitia earum officiis. Fugit magnam totam aut deserunt eum porro.
                                </p>
                                <div class="author">
                                    <img src="/src/image/nytimes-logo-white-xsmall.png" alt="">
                                    <p class="mb-0">
                                        Justine Kilpatrick,
                                        <span class="green">
                                            The New York Times
                                        </span>
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-xl-5 col-md-12 col-sm-12">
                    <div class="other-authors">
                        <div class="block" v-for="author in authors">
                            <div class="box">
                                <h5>
                                    {{ author.title }}
                                </h5>
                                <p class="mb-0">
                                    {{ author.text }}
                                </p>
                            </div>
                            <div class="author">
                                <img :src="author.image" alt="">
                                <p class="mb-0">
                                    {{ author.name }},
                                    <span>
                                        {{ author.subname }}
                                    </span>
                                </p>
                            </div>
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
        padding-top: 70px;
        padding-bottom: 70px;

        .row {
            justify-content: space-between;

            & > * {
                padding-right: 3rem !important;
                padding-left: 3rem !important;
            }

            h3 {
                font-size: 40px;
                margin-bottom: 25px;
                font-family: $family-playfair;
                font-weight: 800;
                color: black;
            }

            p.green {
                font-size: 18px;
                color: $green;
                margin-bottom: 30px;
            }

            button {
                line-height: 42px;
                padding: 0 40px;
                font-size: 14px;
                border: 0;
                background-color: $yellow;
                align-self: flex-end;
                border-radius: 5px;
                color: white;

                &:hover {
                    background-color: $dark-yellow;
                }
            }
        }

        [class^="col"] {
            .card {
                border: 0;
                height: 100%;
                position: relative;

                &:hover img.big-image {
                    transform: scale(1.025);
                    filter: drop-shadow(5px 5px 6px rgb(33, 20, 20));
                    transition: 0.5s;
                    filter: grayscale(30%)
                }
            }

            img.big-image {
                border-radius: 0 0 90px 0;
                transform: scale(1);
                transition: 0.5s;
                height: 100%;
                object-fit: cover;
                filter: grayscale(30%)
            }

            .card-img-overlay{
                padding: 110px 95px;

                    h2 {
                        font-size: 40px;
                        font-family: $family-playfair;
                        font-weight: 500;

                        &::after {
                            content: '';
                            display: block;
                            width: 100%;
                            height: 1px;
                            background-color: rgba( #ffffff, 0.5);
                            margin: 40px 0;
                        }
                    }

                    p {
                        font-size: 20px;
                        margin-bottom: 25px;
                    }

                    .author {
                        display: flex;
                        align-items: center;
                        gap: 12px;
                        padding-top: 20px;

                        p {
                            font-weight: 600;

                            .green {
                                color: $green;
                                font-weight: 500;
                            }
                        }
                    }
                }
            }

            [class^="col"] {

                .other-authors {
                    display: flex;
                    flex-direction: column;

                    .block {
                        margin-bottom: 50px;

                        .box {
                            padding: 50px;
                            background-color: $rose;
                            text-align: center;
                            position: relative;

                            &::after {
                                content: '';
                                display: block;
                                width: 20px;
                                height: 20px;
                                background-color: $rose;
                                position: absolute;
                                bottom: -6px;
                                transform: rotate(45deg);
                            }

                            h5 {
                                font-family: 'Playfair Display', serif;
                                font-size: 25px;
                                font-weight: 700;
                            }

                            p {
                                line-height: 1.7;
                                font-size: 18px;
                                color: rgba( #000000, 0.6);
                                font-weight: 400;
                            }
                        }
                        .author {
                            display: flex;
                            align-items: center;
                            gap: 25px;
                            padding-top: 10px;
                            font-size: 20px;
                        
                            p {
                                font-weight: 500;
                                color: rgba( #000000, 0.6);

                                span {
                                    font-weight: normal;
                                    color: black;
                                }
                            }
                        }
                    }
                }
            }
        }


        @media (max-width: 1200px) {
            .container {
                padding: 50px 12%;
            }

            .card-img-overlay {
                padding: 90px 60px !important;
            }

            button {
                width: 100%;
                margin-bottom: 50px;
            }

            .best-author {
                margin-bottom: 40px;
            }
        }

</style>