<template>
  <div class="app">
    <div class="container-fluid" id="hero">
        <div class="column-d-flex justify-content-center text-center">
            <div class="col-md">
                <h3>Recipe App</h3>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Satisfy&display=swap');
#hero{
    background:url('https://images.unsplash.com/photo-1540660290370-8aa90e451e8a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80');
    background-position:cover;
    background-size:cover;
    background-repeat:no-repeat;
    object-fit:contain;
    padding:100px;
    font-family: 'Satisfy', cursive;
}
#hero h3{
    font-size:40px;
    font-weight:lighter;
}
</style>