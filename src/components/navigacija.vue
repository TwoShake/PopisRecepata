<template>
    <b-navbar>
        <template slot="start">
            <b-navbar-item href="#">
                Svaštara
            </b-navbar-item>
            <b-navbar-item href="#">
            Slastice
            </b-navbar-item>
            <b-navbar-item href="#">
            Pića
            </b-navbar-item>
        </template>
    </b-navbar>
</template>
<script>
export default {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar{
    padding-top: 50px;
    background-color: black;
}
b-navbar-item{
    padding:12px;
    margin-left:20px;
    font-size:40px;
    color:white;
}
</style>
