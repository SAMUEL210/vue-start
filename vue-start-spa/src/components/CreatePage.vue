<template>
    <div class="container nb-3 m-4">
        <div class="row">
            <div class="col-md-8">
                <div class="mb-3">
                    <label for="" class="form-label">
                        Page Title
                    </label>
                    <input 
                        type="text" 
                        class="form-control"
                        v-model="pageTitle"
                    >
                </div>
                <div class="mb-3">
                    <label for="" class="form-label">
                        Description
                    </label>
                    <textarea
                        class="form-control"
                        rows="5"
                        v-model="pageDescription"
                    ></textarea>
                </div>
            </div>
            <div class="col">
                <div class="mb-3">
                    <label for="" class="form-label">
                        Link Text
                    </label>
                    <input 
                    type="text"
                    class="form-control"
                    v-model="linkText">
                    
                </div>
                <div class="mb-3">
                    <label for="" class="form-label">
                        Link URL
                    </label>
                    <input 
                    type="text"
                    class="form-control"
                    v-model="linkUrl">
                    
                </div>

                <div class="row nb-3">
                    <div class="form-check">
                        <input class="form-check-input" type="checkbox" >
                        <label class="form-check-label" for="gridCheck1">
                            Published
                        </label>
                    </div>
                </div>
            </div>
            
            <div class="mb-3">
                <button 
                class="btn btn-primary"
                :disabled="isFormInvalid"
                @click.prevent="submitForm">
                    Create Page
                </button>
            </div>
            
        </div>
    </div>
</template>

<script>

export default {
    props: [ 'pageCreated' ],
    computed: {
        isFormInvalid(){
            return!this.pageTitle || !this.pageDescription || !this.linkText || !this.linkUrl;
        }
    },
    data(){
        return({
            pageTitle: '',
            pageDescription: '',
            linkText: '',
            linkUrl: ''
        });
    },
    methods: {
        submitForm(){
            if(!this.pageTitle || !this.pageDescription || !this.linkText || !this.linkUrl){
                alert("Remplissez svp les champs!")
                return;
            }

            this.pageCreated({
                pageTitle: this.pageTitle,
                pageDescription: this.pageDescription,
                link: {
                    text: this.linkText,
                    url: this.linkUrl
                }
            });
        }
    }
}
</script>