<template>
  <div class="app">
    <div class="container-fluid" id="search">
      <div class="column d-flex justify-content-center text-center">
        <div class="col-md-6">
          <input type="text" placeholder="Search Recipe..." v-model="query" />
          <input
            type="button"
            value="Search"
            @click.prevent="searchRecipe(e)"
          />
        </div>
      </div>
    </div>
    <div class="container-fluid">
      <div class="row d-flex justify-content-center">
        <div class="col-md-12 text-center">
          <h3 v-if="this.query.length>0">Showing Results for {{this.query}}...</h3>
        </div>
        <div
          class="col-sm-6 col-md-3"
          v-for="recipes in recipe"
          :key="recipes.recipe.id"
        >
          <div class="card">
            <img
              :src="recipes.recipe.image"
              class="img-fluid"
              :alt="recipes.recipe.label"
            />

            <div class="card-body">
              <h3>{{ recipes.recipe.label }}</h3>
              <p
                v-for="recipes in recipes.recipe.ingredientLines"
                :key="recipes"
              >
                {{ recipes }}
              </p>
              <b>Source: {{ recipes.recipe.source }}</b>
              <br />
              <a :href="recipes.recipe.url"
                ><button class="btn btn-primary">View Source</button></a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      query: "",
      recipe: [],
      error: `Please enter a valid Recipe`,
    };
  },
  methods: {
    searchRecipe(e) {
      if (this.query.length <= 0 || this.query === this.recipe) {
        alert(this.error);
      } else {
        fetch(
          `https://api.edamam.com/search?q=${this.query}&app_id=54746f42&app_key=ee2be6bd51262229750b0f60e65f89a0&to=20`
        )
          .then((response) => response.json())
          .then((data) => (this.recipe = data.hits));
        return (this.query = "");
      }
    },
  },
};
</script>

<style>
#search {
  margin-bottom: 30px;
  margin-top: 20px;
}
input[type="text"] {
  width: 70%;
  padding: 10px;
}
input[type="button"] {
  padding: 10px;
  font-weight: bold;
}
.card{
  margin: 20px !important;
  margin-bottom:40px;
  padding:2px;
  margin-bottom:30px;
  min-height: 80%;
  max-height:80%;
  text-align: left;
}
.img-fluid{
    min-height:100%;
    max-height:100%;
}
.btn {
  margin-top: 30px;
}
</style>