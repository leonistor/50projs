<script>
  import cardsJson from './assets/cards.json'
  $: cards = cardsJson
  let activeIndex = 0
</script>

<div class="panel">
  {#each cards as { title, image }, i}
    <div
      class="card"
      on:click={() => (activeIndex = i)}
      class:active={i === activeIndex}
      style="background-image: url({image});"
    >
      <h3>{title}</h3>
    </div>
  {/each}
</div>

<style>
  @import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

  .panel {
    font-family: 'Muli', sans-serif;
    font-display: flex;
    height: 80vh;
    padding: 1em;
    display: flex;
    gap: 0.5em;
  }
  .card {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    border-radius: 20px;
    cursor: pointer;
    flex: 0.5;
    transition: all 700ms cubic-bezier(0.075, 0.82, 0.165, 1);
  }
  .card.active {
    flex: 5;
  }
  .card h3 {
    position: absolute;
    font-size: 3em;
    bottom: 20px;
    left: 20px;
    opacity: 0;
  }
  .card.active h3 {
    opacity: 1;
    transition: opacity 0.3s ease-in 0.4s;
  }
</style>
