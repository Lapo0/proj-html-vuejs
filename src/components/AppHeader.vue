<script>
    import store from '../store'

    import NavHeader from '/src/components/NavHeader.vue'

    import Logo from '/src/components/Logo.vue'

    export default {
        data() {
            return {
                store,
                activeLinkIndex: 0,
            }
        },
        computed: {
            links() {
                return this.store.linksNav
            }
        },components: {
            Logo,
            NavHeader,
        },
        methods: {
            isActive(i) {
                this.activeLinkIndex = i
                console.log(this.activeLinkIndex)
            },
        }
    }
</script>

<template>
    <div class="header-black bg-black text-light">
        <div class="top-header align-items-center d-sm-flex d-md-flex d-xl-none">
            <Logo />
            <div class="nav">
                <div class="hamburger fs-1">
                    <i class="fa-solid fa-bars"></i>
                </div>
                <ul class="d-none">
                    <NavHeader :class="activeLinkIndex === i ? 'active' : ''" v-for="(link, i) in links" :key="i" :link="link" @click="isActive(i)"/>
                </ul>
            </div>
        </div>
    </div>

    <header class="text-light">
        <div class="bg-background">
            <div class="opacity"></div>
            <img src="src/image/hero-07-2x.jpg" alt="">
        </div>
        <div class="top-header d-sm-none d-md-none d-xl-flex">
            <Logo />
            <div class="nav">
                <ul>
                    <NavHeader :class="activeLinkIndex === i ? 'active' : ''" v-for="(link, i) in links" :key="i" :link="link" @click="isActive(i)"/>
                    <li>
                        <a href="#">
                            <i class="fa-solid fa-cart-shopping"></i>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
        <div class="bottom-header container-fluid">
            <div class="row h-100 justify-content-xl-end justify-content-md-center justify-content-sm-center">
                <div class="col-md-12 col-xl-6 align-self-center px-sm-5">
                    <h2>
                        Damon Vaughn
                    </h2>
                    <blockquote>
                        Best-Selling Author And The Most Influential Public Intellectual In The Western World Right Now.
                        <p>
                            - The New York Times
                        </p>
                    </blockquote>
                </div>
                <div class="col-md-12 col-xl-6 amazon-coockie">
                    <div class="block">
                        <div class="container-fluid">
                            <div class="up">
                                <div class="image col-6">
                                    <img src="/src/image/book-widget.png" alt="">
                                </div>
                                <div class="text col-6">
                                    <h5 class="text-black">
                                        Latest Book Release
                                    </h5>
                                    <p class="yellow">
                                        D. VAUGHN AUTOBIOGRAPHY
                                    </p>
                                    <p class="text">
                                        Donec fringilla nunc eu turpis dignissim, at euismod sapien tincidunt. Maecenas eleifend congue cursus.
                                    </p>
                                </div>
                            </div>
                        </div>
                        <div class="container-fluid">
                            <div class="buttons">
                                <div class="col-6">
                                    <button>
                                        <i class="fa-brands fa-amazon"></i>
                                        Buy On Amazon
                                    </button>
                                </div>
                                <div class="col-6">
                                    <button>
                                        <i class="fa-brands fa-apple"></i>
                                        Buy On AppStore
                                    </button>
                                </div>
                            </div>
                        </div>
                        
                    </div>
                </div>
            </div>
                
        </div>
        
    </header>

</template>

<style lang="scss">

    @use '/src/style/partials/_variables.scss' as *;

    .logo {
        width: 125px;
    }

    header {
        height: 100vh;
        position: relative;

        .bg-background img{
            object-fit: cover;
            height: 100vh;
            object-position: center;
            position: absolute;
            z-index: -999;
        }

        .bg-background .opacity {
            position: absolute;
            height: 100vh;
            width: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.2), rgba(0,0,0,1));
            z-index: -998;
        }

        .top-header {
            display: flex;
            justify-content: space-between;
            padding: 0 120px;
            height: 10vh;

            .nav ul{
                display: flex;

                & > * {
                    padding: 0 20px;

                    &::before {
                        content: '';
                        display: block;
                        width: 100%;
                        height: 5px;
                        background-color: $yellow;
                        margin-bottom: 40px;
                        filter: opacity(0);
                    }

                    &:hover::before {
                        filter: opacity(1);
                    }

                    &.active::before{
                        filter: opacity(1);
                    }

                    &:hover, a:hover {
                        color: $yellow;
                    }

                    &.active {
                        color: $yellow;
                    }
                }
            }
        }

        .bottom-header {
            height: 90vh;

            h2 {
                font-family: $family-georgia;
                font-size: 90px;
                color: $yellow;
            }

            blockquote {
                font-size: 48px;
                font-family: $family-playfair;
                font-weight: 600;

                p {
                    font-family: $family-monterrat;
                    font-size: 20px;
                    padding-top: 30px;
                    color: rgba(#ffffff,  0.7);
                }
            }

            .amazon-coockie {
                max-width: 700px;
                background-color: white;
                align-self: flex-end;

                .block {
                    padding: 55px 65px;

                    .up, .buttons {
                        display: flex;

                        h5 {
                            font-family: $family-playfair;
                            font-size: 26px;
                            font-weight: 700;
                        }

                        .yellow {
                            color: $yellow;
                            font-family: $family-playfair;
                            font-size: 14px;
                        }

                        p.text {
                            color: rgba(#000000,  0.7);
                        }

                        .col-6 {
                            padding-right: calc(var(--bs-gutter-x) * 0.5);
                            padding-left: calc(var(--bs-gutter-x) * 0.5);
                        }

                        button {
                            line-height: 40px;
                            padding: 0 30px;
                            border: 2px solid $green;
                            border-radius: 6px;
                            width: 100%;

                            &:hover {
                                background-color: $green;
                                color: white;
                            }
                        }
                    }
                }
            }
        }
    }

    @media (max-width: 1200px) {
        .bottom-header {
            height: 100vh !important;
        }
    }

    
</style>