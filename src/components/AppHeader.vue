<script>
    import store from '../store'

    import NavHeader from '/src/components/NavHeader.vue'

    import Logo from '/src/components/Logo.vue'

    export default {
        data() {
            return {
                store,
                activeLinkIndex: '',
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
    <a class="btn btn-primary" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button" aria-controls="offcanvasExample">
  Link with href
</a>

<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>
    <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
  </div>
  <div class="offcanvas-body">
    <div>
      Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists, etc.
    </div>
    <div class="dropdown mt-3">
      <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">
        Dropdown button
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Action</a></li>
        <li><a class="dropdown-item" href="#">Another action</a></li>
        <li><a class="dropdown-item" href="#">Something else here</a></li>
      </ul>
    </div>
  </div>
</div>
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
        <div class="top-header d-sm-none d-md-none d-xl-flex">
            <Logo />
            <div class="nav">
                <ul>
                    <NavHeader :class="activeLinkIndex === i ? 'active' : ''" v-for="(link, i) in links" :key="i" :link="link" @click="isActive(i)"/>
                </ul>
            </div>
        </div>
        <div class="bottom-header px-md-5 px-xl-0 ps-xl-5">
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
                        <div class="buttons">
                            <button class="col-6">
                                <i class="fa-brands fa-amazon"></i>
                                Buy On Amazon
                            </button>
                            <button class="col-6">
                                <i class="fa-brands fa-apple"></i>
                                Buy On AppStore
                            </button>
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

    .top-header {
            display: flex;
            justify-content: space-between;
            max-width: 1700px;
            padding: 0 50px;

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

    header {
        background-image: url(src/image/hero-07-2x.jpg);
        background-size: cover;
        background-position: center;
        height: 100vh;

        

        .bottom-header {
            height: 90vh;

            h2 {
                font-family: $family-georgia;
                font-weight: 400;
                font-size: 90px;
                color: $yellow;
            }

            blockquote {
                font-size: 48px;
                font-family: $family-playfair;

                p {
                    font-family: $family-monterrat;
                    font-size: 20px;
                    padding-top: 30px;
                    color: rgba(#ffffff,  0.7);
                }
            }

            .amazon-coockie {
                max-width: 688px;
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

                        button {
                            line-height: 40px;
                            padding: 0 30px;
                            border: 2px solid $green;
                            border-radius: 6px;

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