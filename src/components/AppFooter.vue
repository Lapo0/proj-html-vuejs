<script>

    import NavFooter from './NavFooter.vue'

    import Logo from '/src/components/Logo.vue'

    export default {
        components: {
            NavFooter,
            Logo,
        }
    }

</script>

<template>
    <footer class="text-light">
        <div class="container-footer">
            <Logo />

            <NavFooter />
            
        </div>
        <p class="text-center">
            © Copyright 2012 - 2023 | Avada Theme by <span>ThemeFusion</span> | All Rights Reserved | Powered by <span>WordPress</span> 
        </p>
      

    </footer>

</template>

<style lang="scss" scoped>

    footer {
        background-image: url(/src/image/footer-3.jpg);
        background-size: cover;
        background-position: top;
        padding: 110px 0 50px 0;
        
        .container-footer {
            margin-left: 125px;
            display: flex;

            .logo {
                min-width: 200px;
            }
        }

        p {
            font-size: 14px;
            padding-top: 65px;

            span {
                color: rgba( #ffffff, 0.4);
            }
        }
    }

    @media (max-width: 1200px) {
        .container-footer {
            display: block !important;
            margin: 0 12%;
        }
    }


</style>