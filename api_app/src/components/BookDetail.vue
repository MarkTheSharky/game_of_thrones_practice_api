<template>
    <section id="book-details">
        <div id="book-cover">
            <img src="../assets/a_game_of_thrones_cover.jpg" :alt="book.name">
        </div>
        <div id="book-info">
            <p>Title: {{book.name}}</p>
            <p v-for="(author, index) in book.authors" :key="index">Author: {{author}}</p>
            <p>Pages: {{book.numberOfPages}}</p>
            <p>Released: {{book.released}}</p>
            <p>Publisher: {{book.publisher}}</p>
            <p>ISBN: {{book.isbn}}</p>
            <character-select :povCharacters="povCharacters"></character-select>
        </div>
    </section>
</template>

<script>
import CharacterSelect from "@/components/CharacterSelect.vue"

export default {
    name: "book-detail",
    props: ['book', "povCharacters"],
    components: {
        "character-select": CharacterSelect
    },
}
</script>

<style scoped>
#book-details {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: 0 50px 0 50px;
}
</style>