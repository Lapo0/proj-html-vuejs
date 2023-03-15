<script>

    export default {
        props: {
            link: {
                type: String,
                required: true,
            }
        },
    }


</script>

<template>

    <li>
        <a href="#">
            {{ link }}
        </a>
    </li>

</template>

<style lang="scss">


</style>