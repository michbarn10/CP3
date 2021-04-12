<template>
  <div>
    <div class="wrapper">
      <!--<div class="search">
        <form class="pure-form">
          <i class="fas fa-search"></i><input v-model="searchText" />
        </form>
      </div>-->
      <div class="dropdown">
        <h2>Pick Your Favorite Genre</h2>
        <h3>See some movies that match</h3>
        <vue-dropdown
          :config="config"
          @setSelectedOption="setNewSelectedOption($event);"></vue-dropdown>
      </div>
    </div>
    <Movie-List :movies="movies" />
  </div>
</template>

<script>
/*import MovieList from "../components/MovieList.vue";
export default {
  name: "Home",
  components: {
    MovieList,
  },
  data() {
    return {
      searchText: "",
    };
  },
  computed: {
    movies() {
      return this.$root.$data.movies
        ? this.$root.$data.movies.filter(
            (movie) =>
              movie.name
                .toLowerCase()
                .search(this.searchText.toLowerCase()) >= 0
          )
        : [];
    },
  },
};
*/
import vueDropdown from "./vue-dropdown/vue-dropdown";
import MovieList from "./MovieList.vue";

export default {
  name: "Home",
  components: {
    vueDropdown,
    MovieList
  },
  data: function() {
    return {
      config: {
        options: [
          {
            value: "Animation"
          },
          {
            value: "Action"
          },
          {
            value: "Romance"
          },
          {
            value: "Comedy"
          },
          {
            value: "Adventure"
          },
          {
            value: "Science-Fiction"
          },
          {
            value: "Fantasy"
          },
        ],
        placeholder: "Genre",
        backgroundColor: "#cde4f5",
        textColor: "black",
        borderRadius: "1.5em",
        border: "1px solid grey",
        width: 250
      }
    };
  },
  computed: {
    movies() {
      return this.$root.$data.movies;
    }
  },
  methods: {
    setNewSelectedOption(selectedOption) {
      this.config.placeholder = selectedOption.value;
      
    },
    setSelectedMovies(selectedOption) {
    }
  }
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
