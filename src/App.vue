<template>
  <ul>
    <favourite-item
      v-for="item in favourites"
      :key="item.id"
      :title="item.title"
      :description="item.description"
      :link="item.link"
    ></favourite-item>
  </ul>
</template>

<script>
import FavouriteItem from './components/favourite-items/FavouriteItem';
export default {
  components: {
    FavouriteItem
  },
  data() {
    return {
      favourites: [
        {
          id: 'facebook',
          title: 'Facebook',
          description: 'A place for you and your friends',
          link: 'https://facebook.com'
        },
        {
          id: 'google',
          title: 'Google',
          description: 'A place to search things, fast and easy',
          link: 'https://google.com'
        }
      ]
    };
  }
};
</script>
