<script>
  export let index = 1
  export let isCompleted = false
  export let isCurrent = false

  const size = 100
  const colors = {
    default: 'dimgray',
    current: 'crimson',
    completed: 'coral'
  }
</script>

<div
  class="step"
  class:isCompleted
  class:isCurrent
  on:click
  style="--size:{size}px;
    --color-default:{colors.default};
    --color-completed:{colors.completed};
    --color-current:{colors.current};
    --fs:{(size * 2) / 3}px"
>
  {index}
</div>

<style>
  .step {
    width: var(--size);
    height: var(--size);
    color: whitesmoke;
    background-color: var(--color-default);
    border-radius: var(--size);
    font-weight: bold;
    font-size: var(--fs);

    text-align: center;
    vertical-align: middle;
    line-height: var(--size);
  }
  .isCompleted {
    background-color: var(--color-completed);
  }
  .isCurrent {
    background-color: var(--color-current);
  }
</style>
