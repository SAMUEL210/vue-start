<template>
    <div class="container" >
        <h1>{{ page.pageTitle }}</h1>
        <p>{{ page.pageDescription }}</p>
    </div>
</template>

<script>
export default {
    props: {
        "page" :{
            type: Object,
            default(rawProps){
                return({
                    "pageTitle" : '',
                    "pageDescription": ''
                });
            } 
        }
    },
}
</script>