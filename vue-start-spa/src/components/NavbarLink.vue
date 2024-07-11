<template>
    <a class="nav-link" :class="activeClasses" aria-current="page" :href="page.link.url"
        :title="`This page move to the ${page.link.text}`">{{ page.link.text }}</a>
</template>

<script>
export default {
    props: ["page", "isActive"],
    computed: {
        activeClasses() {
            return {
                active: this.IsActive,
                emphasize: this.IsActive
            };
        }
    }
}
</script>

<style>
.emphasize {
    text-decoration: underline !important;
}
</style>
