<template>
    <div class="books-list">
        <li class="single-book" v-for="(book, index) in books" :key="index" :book="book">
            <img class=book-image src="https://upload.wikimedia.org/wikipedia/en/9/93/AGameOfThrones.jpg" alt="book.name">
        </li>
    </div>
</template>

<script>
export default {
    name: "books-list-item",
    props: ['books']
}
</script>

<style>
.books-list {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
}

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