<template>
  <ul>
    <favourite-item
      v-for="item in favourites"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :description="item.description"
      :link="item.link"
    ></favourite-item>
  </ul>
</template>

<script>
import FavouriteItem from './FavouriteItem';

export default {
  components: {
    FavouriteItem
  },
  inject: ['favourites']
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
