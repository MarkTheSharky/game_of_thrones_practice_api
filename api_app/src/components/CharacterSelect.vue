<template>
    <div>
        <label for="character-select">Main Characters: </label>
        <select name="character-select" id="character-select" v-on:change="handleClick" v-model="selectedCharacter">
            <option selected disabled value=null>Choose a character for more information:</option>
            <option v-for="(character, index) in povCharacters" :key="index" :value="character">{{character.name}}</option>
        </select>
    </div>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
    name: "character-select",
    props: ['povCharacters'],
    data() {
        return {
            selectedCharacter: null
        }
    },
    methods: {
        handleClick() {
            eventBus.$emit("character-selected", this.selectedCharacter)
        }
    }
}
</script>

<style>

</style>