<script>
  import { Route, router } from 'tinro'
  import ExpandingCards from './ExpandingCards.svelte'
  import Home from './Home.svelte'
  import ProgressSteps from './ProgressSteps.svelte'

  router.mode.hash()
</script>

<nav>
  <a href="/">Home</a>
  <a href="/expanding">Expanding Cards</a>
  <a href="/progress">Progress Steps</a>
</nav>

<main>
  <Route path="/"><Home /></Route>
  <Route path="/expanding"><ExpandingCards /></Route>
  <Route path="/progress"><ProgressSteps /></Route>
</main>

<style>
  :global(#app) {
    display: grid;
    grid-template-rows: 80px 1fr;
    gap: 10px;
    height: 100vh;
    width: 100vw;
  }
  :global(main) {
    background-color: firebrick;
  }

  nav {
    display: inline-flex;
    flex-wrap: wrap;
    gap: 12px;
    padding-left: 20px;
  }
  nav a {
    align-self: center;
    padding: 10px;
    text-decoration: none;
    border-radius: 10px;
    color: white;
    background-color: firebrick;
  }
</style>
