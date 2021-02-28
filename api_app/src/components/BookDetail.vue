<template>
    <section id="book-details">
        <div id="book-cover">
            <img class="book-cover-large" src="../assets/a_game_of_thrones_cover.jpg" :alt="book.name">
        </div>
        <div id="book-info">
            <p>Title: {{book.name}}</p>
            <p v-for="(author, index) in book.authors" :key="index">Author: {{author}}</p>
            <p>Pages: {{book.numberOfPages}}</p>
            <p>Released: {{book.released}}</p>
            <p>Publisher: {{book.publisher}}</p>
            <p>ISBN: {{book.isbn}}</p>
            <character-select v-if="povCharacters.length" :povCharacters="povCharacters"></character-select>
            <character-detail v-if="selectedCharacter" :selecetedCharacter="selectedCharacter"></character-detail>
        </div>
    </section>
</template>

<script>
import CharacterSelect from "@/components/CharacterSelect.vue";
import CharacterDetail from "@/components/CharacterDetail.vue";

export default {
    name: "book-detail",
    props: ['book', "povCharacters", "selectedCharacter"],
    components: {
        "character-select": CharacterSelect,
        "character-detail": CharacterDetail
    },
}
</script>

<style scoped>
#book-details {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: 0 50px 0 50px;
}

.book-cover-large {
    width: 400px;
}
</style>