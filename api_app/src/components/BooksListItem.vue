<template>
    <div class="single-book">
        <li v-on:click="handleClick">
            <!-- <img class=book-image :src="'http://covers.openlibrary.org/b/isbn/' + book.isbn + '-M.jpg'" :alt="book.name"> -->
            <!-- placeholder image to be deleted --><img class=book-image src="../assets/a_game_of_thrones_cover.jpg" :alt="book.name"> 
        </li>
    </div>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
    name: "books-list-item",
    props: ['book'],
    methods: {
        handleClick() {
            eventBus.$emit("book-selected", this.book);
        },
    },
}
</script>

<style>
.single-book {
    height: 150px;
    width: 100px;
    background-color: limegreen;
    border: 1px solid black;
    margin: 5px;
    list-style-type: none;
}

.book-image {
    height: 150px;
    width: 100px;
}

.book-name{
    color: coral;
}
</style>