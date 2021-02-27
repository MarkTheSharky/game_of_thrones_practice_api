<template>
    <div>
        <label for="character-select">Choose a character for more information:</label>
        <select name="character-select" id="character-select">
            <option v-for="(character, index) in povCharacters" :key="index" value="">{{character.name}}</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "character-select",
    props: ['povCharacters']
}
</script>

<style>

</style>