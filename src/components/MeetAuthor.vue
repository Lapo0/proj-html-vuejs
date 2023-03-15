<script>

  

</script>

<template>

  <section>
    <div class="container">
        <div class="row">
            <h2>
                More About Damon Vaughn
            </h2>
            <p class="info-author">
                Damon Vaughn is a professor of psychology at the University of Toronto, a clinical psychologist and the author of the multi-million copy bestseller
                <q>
                    The story of my life.
                </q>
            </p>
            <button class="text-light">
                Meet The Author
            </button>
        </div>
       
    </div>
  </section>

</template>

<style lang="scss" scoped>

    @use '/src/style/partials/_variables.scss' as *;

    .container {
        text-align: center;

        .row {
            flex-direction: column;
            align-items: center;

            h2 {
                font-family: $family-georgia;
                font-weight: 400;
                font-size: 90px;
                color: $yellow;
            }

            .info-author {
                font-size: 30px;
                color: black;
            }

            button {
                line-height: 42px;
                width: 166px;
                border: 0;
                background-color: $green;
                border-radius: 5px;
                margin: 40px 0 130px 0;
                transition: 0.2s;

                &:hover {
                    background-color: $dark-green;
                    transition: 0.2s;
                }
            }
        }
    }

    @media (max-width: 1200px) {
        .row {
            padding: 0 160px;
        }
    }
  

</style>