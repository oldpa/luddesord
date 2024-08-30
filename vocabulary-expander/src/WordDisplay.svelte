<script>
  export let language;
  export let word;

  const flagEmoji = {
    Swedish: "🇸🇪",
    Japanese: "🇯🇵",
    Italian: "🇮🇹",
  };
</script>

<div class="word-display">
  <span class="flag">{flagEmoji[language] || language}</span>
  <p>{word}</p>
</div>

<style>
  .word-display {
    border: 1px solid #ccc;
    padding: 1em;
    margin: 1em 0;
    display: flex;
    align-items: center;
  }

  .flag {
    font-size: 1.5em;
    margin-right: 0.5em;
  }

  p {
    font-size: 1.5em;
    margin: 0;
  }
</style>
