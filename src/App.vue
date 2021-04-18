<template>
  <the-header title="FavouriteSites"></the-header>
  <the-items></the-items>
</template>

<script>
import TheHeader from './components/layouts/TheHeader';
import TheItems from './components/favourite-items/TheItems';

export default {
  components: {
    TheHeader,
    TheItems
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;400&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Poppins', sans-serif;
}

body {
  margin: 0;
}
</style>
