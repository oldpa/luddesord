<script>
  import WordDisplay from "./WordDisplay.svelte";
  import { wordList } from "./wordList.js";

  let currentWords = {};

  function getRandomWord() {
    return wordList[Math.floor(Math.random() * wordList.length)];
  }

  function updateWords() {
    currentWords = getRandomWord();
  }

  // Initialize with a random word
  updateWords();
</script>

<main>
  <h1>Luddes ord</h1>
  <WordDisplay language="Swedish" word={currentWords.swedish} />
  <WordDisplay language="Italian" word={currentWords.italian} />
  <WordDisplay language="Japanese" word={currentWords.japanese} />
  <button on:click={updateWords}>Next Word</button>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 300px;
    margin: 0 auto;
  }
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  button {
    margin-top: 1em;
    padding: 0.5em 1em;
    font-size: 1em;
    background-color: #ff3e00;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #ff6340;
  }
</style>
