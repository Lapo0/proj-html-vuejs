<script>
export default {
    data() {
        return {
            articles: [
                {
                    title: 'What s On Your Booklist?',
                    text: 'October 24th, 2019 |0 comments',
                    image: '/src/image/thumb-13-2x-320x202.jpg',
                },
                {
                    title: 'Instanbul Travel Guide',
                    text: 'October 24th, 2019 |0 comments',
                    image: '/src/image/thumb-08-2x-320x202.jpg',
                },
            ]
        }
    }
}

</script>

<template>
    <section class="rose">
        <div class="container">
            <div class="row">
                <div class="col-auto">
                    <h2>
                        Recent Articles
                    </h2>
                    <p class="green">
                        TESTIMONIALS FROM AROUND THE WORLD
                    </p>
                </div>
                <div class="col-xl-auto col-md-12 col-sm-12 d-flex flex-column justify-content-center">
                    <button>
                        All Articles
                    </button>
                </div>
            </div>
            <div class="row">
                <div class="col-xl-8 d-xl-block d-md-none d-sm-none">
                    <div class="card big h-100">
                        <img src="/src/image/20-Tips-800x471.jpg" class="card-img-top" alt="">
                        <div class="card-body">
                            <h5>
                                20 Creativity Tips
                            </h5>
                            <p class="small-text">
                                By admin|October 24th, 2019|Categories: Event, Tips & Tricks
                            </p>
                            <p class="info-text">
                                Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Donec velit neque, auctor sit amet aliquam vel, ullamcorper sit amet.
                            </p>
                        </div>
                    </div>
                </div>
                <div class="col-xl-4 col-md-12 col-sm-12">
                    <div class="card space h-100">
                        <div class="card-body">
                            <div v-for="article in articles" class="card">
                                <img :src="article.image" class="card-img-top" alt="">
                                <div class="card-body">
                                    <h4>
                                        {{ article.title  }}
                                    </h4>
                                    <p>
                                        {{ article.text  }}
                                    </p>
                                </div>
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

    .rose {
        background-color: $rose;

        .container {
            padding-top: 120px;
            padding-bottom: 100px;

            .row {
                justify-content: space-between;

                & > * {
                    padding-right: 3rem !important;
                    padding-left: 3rem !important;
                }

                h2 {
                    font-family: $family-playfair;
                    font-size: 40px;
                    font-weight: 600;
                }

                p.green {
                    color: $green;
                    margin: 30px 0;
                    font-size: 18px;
                }

                button {
                    line-height: 42px;
                    padding: 0 40px;
                    border: 0;
                    background-color: $yellow;
                    align-self: flex-end;
                    border-radius: 5px;
                    color: white;

                    &:hover{
                        background-color: $dark-yellow;
                    }
                }

                .card {
                    border: 0;

                    img.card-img-top {
                        filter: blur(0);
                        filter: contrast(100%);
                        transition: 0.4s;

                        &:hover {
                            transition: 0.4s;
                            filter: blur(1px);
                            filter: contrast(70%);
                            cursor: pointer;
                        }
                    }

                    h5{
                        font-size: 25px;
                        font-weight: 400;
                    }

                    p.small-text {
                        font-size: 14px;
                    }

                    p.info-text {
                        font-size: 20px;
                        color: rgba($color: #000000, $alpha: 0.7);
                    }
                }

                .card.big {
                    padding: 50px;
                }

                .card.space {
                    padding: 30px;
                }
            }
        }
    }

    @media (max-width: 1200px) {
        .card {
            display: contents;

            .card-body {
                overflow: hidden;
            }

            img {
                transform: scale(1);
                transition: 0.4s;
            }

            img:hover {
                transition: 0.4s;
                transform: scale(1.025);
            }

            .card-body {
                padding: 10px 0;
                margin-bottom: 25px;
            }
        }

        button {
            width: 100%;
            margin-bottom: 50px;
        }
    }


</style>