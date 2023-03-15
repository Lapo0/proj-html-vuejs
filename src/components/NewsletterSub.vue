<script>


</script>

<template>
    <section class="bg-space">
        <div class="container-sm">
            <div class="row">
                <div class="col-6 text-light text-center">
                    <h2>
                        Subscribe To My Newsletter
                    </h2>
                    <p class="yellow mb-0">
                        BE NOTIFIED ABOUT BOOK SIGNING TOUR DATES
                    </p>
                    <form class="row g-3">
                        <div class="col-xl-auto col-md-12 col-sm-12">
                            <input type="email" class="form-control" id="inputEmail" placeholder="Insert your email ... *">
                        </div>
                        <div class="col-xl-auto col-md-12 col-sm-12">
                            <button type="submit" class="btn mb-3 text-light">
                                Subscribe
                            </button>
                        </div>
                    </form>
                    <p class="info mb-0">
                        Donec fringilla nunc eu turpis dignissim, at euismod sapien tincidunt.
                    </p>
                </div>
            </div>
        </div>
    </section>


</template>

<style lang="scss" scoped>

    @use '/src/style/partials/_variables.scss' as *;

    .bg-space {
        background-image: url(/src/image/banner-2.jpg);
        background-size: cover;
        background-position: center;

        .container-sm {
            padding: 100px;

            .row {
                justify-content: center;

                h2 {
                    font-family: $family-playfair;
                    font-size: 40px;
                }

                p.yellow {
                    color: $yellow;
                    padding-bottom: 40px;
                }

                .form-control {
                    border-radius: 3px;
                }

                .form-control, .btn {
                    line-height: 40px;
                    font-size: 18px;
                }

                .btn {
                    background-color: $green;
                    width: 100%;

                    &:hover{
                        background-color: $dark-green;
                    }
                }

                p.info {
                    padding-top: 40px;
                    font-size: 18px;
                    color: rgba( #ffffff, 0.4);
                }


            }
        }
    }

</style>