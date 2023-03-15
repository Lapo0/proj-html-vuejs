<script>
    import MeetAuthor from './MeetAuthor.vue';

    import AudioBook from './AudioBook.vue';

    import Testimonials from './Testimonials.vue';

    import UpcomingEvents from './UpcomingEvents.vue'

    import NewsletterSub from './NewsletterSub.vue'

    import AuthorHimSelf from './AuthorHimSelf.vue'

    import RecentArticles from './RecentArticles.vue'

    export default {
        components: {
            MeetAuthor,
            AudioBook,
            Testimonials,
            UpcomingEvents,
            NewsletterSub,
            AuthorHimSelf,
            RecentArticles,
        }
    }


</script>

<template>
    <main>
        <MeetAuthor />
        <AudioBook />
        <Testimonials />
        <UpcomingEvents />
        <NewsletterSub />
        <AuthorHimSelf />
        <RecentArticles />
    </main>

</template>

<style lang="scss" scoped>

    main {
        padding: 120px 0 0 0;
    }

</style>