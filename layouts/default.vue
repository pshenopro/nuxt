<template>
    <div>
        <Header />
        <Nuxt/>
        <Footer />
    </div>
</template>

<script>
    import Header from '@/components/header'
    import Footer from '@/components/footer'

    export default {
        head: {
            link: [
                {
                    rel: 'stylesheet',
                    href: 'https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@300;400;700&family=Roboto:wght@300;400;700&display=swap'
                }
            ]
        },
        components: {
            Header,
            Footer
        }
    }

</script>

<style>
</style>
