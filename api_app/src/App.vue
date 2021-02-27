<template>
  <main>
    <h1>Game Of Thrones</h1>
    <books-list :books="books"></books-list>
    <book-detail v-if="selectedBook" :book="selectedBook" :povCharacters="povCharacters"></book-detail>
  </main>
</template>

<script>
import { eventBus } from "@/main.js";
import BooksList from "@/components/BooksList.vue";
import BookDetail from "@/components/BookDetail.vue";
import Characterdetail from "@/components/CharacterDetail.vue";
import MainCharacters from "@/components/MainCharacters.vue";

export default {
  name: 'app',
  components: {
    "books-list": BooksList,
    "book-detail": BookDetail
  },
  data() {
    return {
      books: [],
      selectedBook: null,
      povCharacters: []
    }
  },
  methods: {
    getGameOfThronesBooks() {
      fetch('https://www.anapioficeandfire.com/api/books?page=1&pageSize=50')
      .then((res) => res.json())
      .then((data) => (this.books = data))
    },
    getGameOfThronesCharacter(characterAPI) {
      fetch(characterAPI)
      .then((res) => res.json())
      .then((data) => (this.povCharacters.push(data)))
    }
  },
  mounted() {
    this.getGameOfThronesBooks();

    eventBus.$on("book-selected", (book) => {
      this.selectedBook = book
    }),
    eventBus.$on("characterAPI-handler", (characterAPIs) => {
      this.povCharacters = []
      characterAPIs.forEach((characterAPI) => {
        this.getGameOfThronesCharacter(characterAPI)
      })
    })
  }
}
</script>

<style>

</style>