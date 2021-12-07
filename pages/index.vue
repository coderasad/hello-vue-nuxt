<template>
    <div  class="main-container">
        <Header/>
        <h4>Index page</h4>
        <Footer/>
    </div>
</template>

<script>
import Header from "../components/Header";
import Footer from "../components/Footer";
export default {
    name: "index",
    components: {Footer, Header}
}
</script>

<style scoped>

</style>