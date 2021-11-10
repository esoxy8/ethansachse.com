<template>
    <div class="caption">
        <h3>{{prj.name}}</h3>
        <p>{{prj.description}} coded in {{prj.language}}.</p>
        <p><button @click="toRepo()" class="btn btn-outline-primary" type="button"><i class="bi bi-github icons"></i></button></p>
    </div>
</template>

<script>
export default {
    name: 'Project',
    props: {  
        prj: {
            name: String,
            description: String,
            language: String,
            url: String
        }
    },
    methods: {
        toRepo() {
            window.open(this.prj.url, '_blank');
        }
    }
}
</script>

<style scoped lang="scss">
@import "@/styles/main.scss";
@import 'node_modules/bootstrap/scss/bootstrap.scss';

.caption {

    @media only screen and (max-width: 700px) {
        /* if screen is less than 700px in width */
        width: 95%;
        padding: 2.5%;
        margin: 2.5%;
    }

    width: 45%;
    padding: 2.5%;
    margin: 2.5%;
    text-align: center;
    border: 2px solid $lavendar;
    border-radius: 8px;

    h3 {
        color: $turquoise;
    }

    p {
        color: $lavendar;
        font-size: 18px;
    }

    .btn {
        // color: $turquoise !important;
        // outline-color: $turquoise !important;

        i {
            //color: $turquoise !important;
        }
    }
}
</style>