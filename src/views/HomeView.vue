<template>
  <Header/>
  <Search/>
  <Footer/>
</template>

<script>
import Header from '@/components/Header.vue'
import Search from '@/components/Search.vue'
import Footer from '@/components/Footer.vue'
export default {
  components:{
    Search, Header, Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Edu+VIC+WA+NT+Beginner&display=swap');
body{
  margin:0;
  padding:0;
  overflow-x:hidden;
  scroll-behavior: smooth;
  font-family: 'Edu VIC WA NT Beginner', cursive !important;
}
</style>