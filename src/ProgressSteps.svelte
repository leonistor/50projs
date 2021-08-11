<script>
  import Step from './Step.svelte'

  let steps = ['Look', 'Touch', 'Kiss', 'Swallow']
  let current = 0
  let message = 'Please proceed'
</script>

<div class="content">
  <div class="foo">
    <h3>Progress steps</h3>
    <pre>{message}</pre>

    {#each steps as step, i}
      <Step index={i + 1} />
    {/each}

    <div class="btns">
      <button class="btn">&lt;</button>
      <button class="btn">&gt;</button>
    </div>
  </div>
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Asap:wght@400;700&display=swap');
  .foo {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .content {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    font-family: 'Asap', sans-serif;
  }
</style>
