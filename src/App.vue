<template>
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="/Images/Llama.jpg" />
        </router-link>
        <ul>
          <li><router-link to='/'>HOME</router-link></li>
          <li><router-link to="/browse">CUSTOMIZE</router-link></li>
          <li><router-link to="/theatre">WATCH LATER</router-link></li>
        </ul>
      </div>
      <div id="side">
        <router-link to="/browse">
          <div class="menu-item browse">
            <img src="/images/globe.png" />
            <p>Customize</p>
          </div>
        </router-link>
        <router-link to="/theatre">
          <div class="menu-item">
            <img src="/images/love.png" />
            <p>
              {{ this.$root.$data.theatre ? this.$root.$data.theatre.length : 0 }}
              Movies
            </p>
          </div>
        </router-link>
      </div>
    </div>
    <router-view />
    <footer>
      <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
      <a
        href="https://github.com/BYU-CS-260-Winter-2021/lab-3b-grocery-store-michbarn10"
        >GitHub</a
      >
    </footer>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>
