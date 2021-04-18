<template>
  <base-card>
    <base-button
      @click="setSelectedItem('stored-items')"
      :mode="selectedButtonMode"
      >Stored sites</base-button
    >
    <base-button @click="setSelectedItem('add-items')" :mode="addButtonMode"
      >Add sites</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedItem"></component>
  </keep-alive>
</template>

<script>
import AddItems from './AddItems';
import StoredItems from './StoredItems';
export default {
  components: {
    AddItems,
    StoredItems
  },
  data() {
    return {
      selectedItem: 'stored-items',
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
  },
  computed: {
    selectedButtonMode() {
      return this.selectedItem === 'stored-items' ? null : 'flat';
    },
    addButtonMode() {
      return this.selectedItem === 'add-items' ? null : 'flat';
    }
  },
  provide() {
    return {
      favourites: this.favourites,
      addItems: this.addItems,
      removeItems: this.removeItems
    };
  },
  methods: {
    setSelectedItem(item) {
      this.selectedItem = item;
    },
    addItems(title, description, link) {
      const newItems = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link
      };
      this.favourites.unshift(newItems);
      this.selectedItem = 'stored-items';
    },
    removeItems(itemId) {
      const removedItems = this.favourites.findIndex(res => res.id === itemId);
      this.favourites.splice(removedItems, 1);
    }
  }
};
</script>
