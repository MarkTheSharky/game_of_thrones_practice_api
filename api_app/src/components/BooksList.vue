<template>
    <section>
        <ul>
            <books-list-item :books="books"></books-list-item>
        </ul>
    </section>
</template>

<script>
import BooksListItem from "@/components/BooksListItem.vue";

export default {
    name: "all-books",
    components: {
        "books-list-item": BooksListItem
    },
    props: ['books']
    
}
</script>

<style>

</style>