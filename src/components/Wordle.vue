<template>
    <div>
        <p v-if="wordleWord">The Wordle of the day is: {{ wordleWord }}</p>
        <button v-if="!wordleWord" @click="getWord">Click Me for the Word</button>
    </div>
  
</template>

<script>
import wordList from "../wordlists/wordle.json";
import { ref } from "vue";
import { defineComponent } from '@vue/composition-api';

export default defineComponent({
    name: 'WordGenerator',
    setup() {
        let wordleWord = ref(false);

        function getWord () {
            const t = new Date();
            const today = new Date(t).setHours(0, 0, 0, 0);
            const oldDate = new Date(2021, 5, 19, 0, 0, 0);
            const subtractor = new Date(oldDate).setHours(0, 0, 0, 0);
            const wordIndex = Math.round((today - subtractor) / 864e5);
            wordleWord.value = wordList.words[wordIndex].toUpperCase();
        }
        return {    
            getWord,
            wordleWord,
        };
    },
});
</script>

<style>

</style>