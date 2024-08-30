<script>
  export let language;
  export let word;
</script>

<div class="word-display">
  <h2>{language}</h2>
  <p>{word}</p>
</div>

<style>
  .word-display {
    border: 1px solid #ccc;
    padding: 1em;
    margin: 1em 0;
  }
</style>
