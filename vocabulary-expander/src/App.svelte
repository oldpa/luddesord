<script>
  import WordDisplay from "./WordDisplay.svelte";
  import { wordLists } from "./wordLists.js";

  let currentWords = {};
  let selectedList = "basicWords";

  function getRandomWord() {
    const currentWordList = wordLists[selectedList];
    return currentWordList[Math.floor(Math.random() * currentWordList.length)];
  }

  function updateWords() {
    currentWords = getRandomWord();
  }

  // Initialize with a random word
  updateWords();
</script>

<main>
  <h1>Luddes ord</h1>
  <select bind:value={selectedList} on:change={updateWords}>
    <option value="basicWords">Basic Words</option>
    <option value="colors">Colors</option>
    <option value="numbers">Numbers</option>
    <option value="animals">Animals</option>
    <option value="foodAndDrink">Food and Drink</option>
    <option value="bodyParts">Body Parts</option>
    <option value="clothing">Clothing</option>
    <option value="weather">Weather</option>
    <option value="professions">Professions</option>
    <option value="transportation">Transportation</option>
    <option value="furniture">Furniture</option>
    <option value="emotions">Emotions</option>
    <option value="family">Family</option>
    <option value="sports">Sports</option>
    <option value="technology">Technology</option>
    <option value="nature">Nature</option>
    <option value="hobbies">Hobbies</option>
    <option value="countries">Countries</option>
    <option value="school">School</option>
    <option value="time">Time</option>
    <option value="music">Music</option>
    <option value="vehicles">Vehicles</option>
    <option value="verbs">Verbs</option>
  </select>
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
  select {
    margin-bottom: 1em;
    padding: 0.5em;
    font-size: 1em;
  }
</style>
