<template>
    <div>
        <label for="character-select">Choose a character for more information:</label>
        <select name="character-select" id="character-select">
            <option v-for="(character, index) in characters" :key="index" value="">{{character}}</option>
        </select>
        <!-- <p v-for="(character, index) in characters" :key="index"></p> -->
    </div>
</template>

<script>
export default {
    name: "character-select",
    props: ['characters']
}
</script>

<style>

</style>