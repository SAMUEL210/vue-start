<template>
    <navbar :pages="pages" :active-page="activePage" :nav-link-click="(index) => activePage = index">
    </navbar>

    <page-viewer :page="pages[activePage]"></page-viewer>
</template>

<script>
import Navbar from './components/Navbar.vue';
import PageViewer from './components/PageViewer.vue';

export default {
    components: {
        Navbar,
        PageViewer
    },

    data() {
        return ({
            activePage: 0,
            pages: [
                {
                    link: { text: 'Home', url: 'index.html' },
                    pageTitle: 'Home Page',
                    pageDescription: "Ceci est la page d'accueil!"
                },
                {
                    link: { text: 'About', url: 'about.html' },
                    pageTitle: 'About page',
                    pageDescription: "Ceci est la page About"
                },
                {
                    link: { text: 'Contact', url: 'contact.html' },
                    pageTitle: 'Contact page',
                    pageDescription: "Ceci est la page Contact"
                },
                {
                    link: { text: 'Blog', url: 'blog.html' },
                    pageTitle: 'Blog page',
                    pageDescription: "Ceci est la page Blog"
                }
            ]
        })
    }
}
</script>