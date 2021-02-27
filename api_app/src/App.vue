<template>
  <main>
    <h1>Game Of Thrones</h1>
    <books-list :books="books"></books-list>
  </main>
</template>

<script>
// import { eventBus } from "@/main.js";
import BooksList from "@/components/BooksList.vue";
import BookDetail from "@/components/BookDetail.vue";
import Characterdetail from "@/components/CharacterDetail.vue";
import MainCharacters from "@/components/MainCharacters.vue";

export default {
  name: 'app',
  components: {
    "books-list": BooksList,
    // "book-detail": BookDetail
  },
  data() {
    return {
      books: [],
    }
  },
  methods: {
    getGameOfThronesBooks() {
      fetch('https://www.anapioficeandfire.com/api/books?page=1&pageSize=50')
      .then((res) => res.json())
      .then((data) => (this.books = data))
    }
  },
  mounted() {
    this.getGameOfThronesBooks()
  }
}
</script>

<style>

</style>