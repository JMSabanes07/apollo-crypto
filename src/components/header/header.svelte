<script>
  import Nav from './nav.svelte'
  import ApolloLogo from './apolloLogo.svelte'
</script>

<header>
  <div class="col">
    <ApolloLogo />
    <Nav />
  </div>
</header>

<style>
  header {
    display: flex;
    justify-content: center;

    width: 100%;
    background: rgba(0, 0, 0, 0);
    position: fixed;
    top: 0;
    z-index: 999;
  }
  .col {
    display: grid;
    grid-template-columns: auto 1fr;
    padding: 1rem;
    backdrop-filter: blur(10px);
    width: 100%;
    max-width: 1200px;
  }
</style>
