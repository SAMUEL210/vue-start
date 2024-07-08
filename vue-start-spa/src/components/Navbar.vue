<template>
    <nav :class="[`navbar navbar-expand-lg`, `navbar-${theme}`, `bg-${theme}`]">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item" v-for="(page, index) in pages" key="index">
                    <a class="nav-link" :class="{ active: activePage == index }" aria-current="page"
                        :href="page.link.url" :title="`This page move to the ${page.link.text}`"
                        @click.prevent="navLinkClick(index)">{{ page.link.text }}</a>
                </li>
            </ul>
            <form class="d-flex">
                <button class="btn btn-primary" @click.prevent="changeTheme()">Toogle Nav</button>
            </form>
        </div>
    </nav>
</template>

<script>
export default {
    props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'dark',
        }
    },
    methods: {
        changeTheme() {
            let theme = 'light';
            if (this.theme == 'light') {
                theme = 'dark';
            }

            this.theme = theme;
        }
    }
}
</script>