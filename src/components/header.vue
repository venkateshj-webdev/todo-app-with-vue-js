<template>
    <div class="container-fluid">
        <div class="row">
            <div class="navbar navbar-dark bg-primary">
                 <h3 class="text-white m-auto">{{title}}</h3>
            </div>
        </div>
    </div>
</template>
<script>


export default {
    name: 'headerCOmponent',
    props: {
    },
    data() {
        return {
            title: 'Todo Application'
        }
    },
    methods: {

    }

}
</script>

<style scoped>

</style>


