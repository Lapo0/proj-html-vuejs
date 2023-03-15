<script>

    export default {
        data() {
            return {
                cards: [
                    {
                        image: '/src/image/event-05.jpg',
                        title: 'Chicago Book Signing',
                        text: 'Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a. Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a nulla.',
                    },
                    {
                        image: '/src/image/event-04.jpg',
                        title: 'Meet & Greet With Amanda',
                        text: 'Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a. Praesent sapien massa, convallis a pellentesque nec, egestas.',
                    },
                    {
                        image: '/src/image/event-07.jpg',
                        title: 'Open Book: Dialogues',
                        text: 'Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a. Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a nulla.',
                    },
                    {
                        image: '/src/image/event-06.jpg',
                        title: 'New York Bookstore Opening',
                        text: 'Sed porttitor lectus nibh. Praesent sapien massa, convallis a pellentesque nec, egestas non nisi. Cras ultricies ligula sed.',
                    },
                ]
            }
        }
    }

</script>

<template>
    <section class="rose">
        <div class="container-xl">
            <h2>
                Upcoming Events
            </h2>
            <p class="yellow">
                MEET THE AUTHOR IN PERSON
            </p>
            <div class="grid">
                <div v-for="card in cards" class="card">
                    <img :src="card.image" class="card-img-top" alt="">
                    <div class="card-body">
                        <h4>
                            {{ card.title  }}
                        </h4>
                        <p class="card-text">
                            {{ card.text  }}
                        </p>
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

        .container-xl {
            padding: 80px 0;
            text-align: center;

            h2 {
                font-family: 'Playfair Display', serif;
                font-size: 40px;
                font-weight: 600;
                color: black;
            }

            .yellow {
                font-size: 18px;
                color: $yellow;
            }

            .grid {
                display: grid;
                grid-template-columns: repeat(3, 1fr);
                gap: 50px;
                margin-top: 50px;
                padding: 0 12%;

                & > *:last-child {
                    display: none;
                }

                .card, img {
                    border-radius: 0;
                    border: 0;
                }

                img {
                    filter: blur(0);
                    filter: contrast(100%);
                    transition: 0.4s;
                }

                img:hover {
                    transition: 0.4s;
                    filter: blur(1px);
                    filter: contrast(70%);
                    cursor: pointer;
                }

                .card-body {
                    padding: 35px;

                    h4::after {
                    content: '';
                    display: block;
                    width: 100%;
                    height: 1px;
                    background-color: rgba( #000000, 0.1);
                    margin: 20px 0;
                    }
                }

                @media (max-width: 1200px) {
                    grid-template-columns: repeat(2, 1fr);

                    & > *:last-child {
                    display: block;
                    }
                }
            }
        }
    }


</style>