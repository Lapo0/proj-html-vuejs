<script>

export default {
    data() {
        return {
            links: [
                'Latest Book',
                'Upcoming Events',
                'Recent Articles',
                'Business Enquiries',
                'Visit My Foundation',
            ],
            contactInfo: [
                '63 E. Studebaker Street Bolingbrook, IL 60440',
                'Phone: (800) 000-0000',
                'Mobile: (800) 000-0000',
                'Email: info@your-company.com',
            ]
        }
    }
}


</script>

<template>

    <section class="text-light">
        <div class="about-me">
            <h5>
                ABOUT ME
            </h5>
            <p>
                Vivamus suscipit tortor eget felis porttitor volutpat. Nulla quis lorem ut libero malesuada feugiat. Vivamus suscipit tortor eget felis porttitor volutpat.
            </p>
        </div>
        <div class="links">
            <h5>
                USEFUL LINKS
            </h5>
            <ul>
                <li v-for="link in links">
                    icon {{ link }}
                </li>
            </ul>
        </div>
        <div class="contact-info">
            <h5>
                CONTACT INFO
            </h5>
            <ul>
                <li v-for="contact in contactInfo">
                    {{ contact }}
                </li>
                <li>
                    <ul class="icon">
                        <li v-for="icon in 5">
                            {{ icon  }}
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </section>

</template>

<style lang="scss" scoped>

@use '/src/style/partials/_variables.scss' as *;

    section {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 110px;
        max-width: 1250px;
        margin: 0 auto;

        h5 {
            font-family: $family-playfair-SC;
            font-size: 24px;
            font-weight: 500;
            margin-bottom: 30px;
        }

        p {
            line-height: 30px;
            font-weight: 500;
            color: rgba($color: #ffffff, $alpha: 0.7);
        }

        ul {
            padding: 0;

            & > * {
                line-height: 40px;
                color: rgba($color: #ffffff, $alpha: 0.7);
            }
        }

        ul.icon {
            display: flex;
            margin-left: -10px;

            & > * {
                margin: 0 10px;
            }
        }
    }

    @media (max-width: 1200px) {
        section {
            grid-template-columns: repeat(1, 1fr);
        }
    }
    


</style>