<script>
  import { link, useLocation } from 'svelte-navigator'

  let location = useLocation()

  const links = [
    {
      pathname: '/',
      name: 'Home',
    },
    {
      pathname: '/coins',
      name: 'Coins',
    },
    {
      pathname: '/coins/recently',
      name: 'Recently Added',
    },
    {
      pathname: '/coins/trending',
      name: 'Large Movers',
    },
    {
      pathname: '/coins/categories',
      name: 'Categories',
    },
  ]
</script>

<nav>
  <ul>
    {#each links as { pathname, name }}
      <li class={$location.pathname === pathname ? 'selected' : ''}>
        <a href={pathname} use:link>{name}</a>
      </li>
    {/each}
  </ul>
</nav>

<style>
  nav {
    align-self: center;
    justify-self: flex-end;
  }

  ul {
    display: flex;
    gap: 1.5rem;
  }

  li {
    display: grid;
    justify-content: center;
    position: relative;
  }

  li::after {
    content: '';
    position: absolute;
    bottom: -15px;
    width: 0%;
    height: 2px;
    background-color: rgb(0, 255, 157);
    transition: 0.3s;
    left: 0;

    filter: drop-shadow(0px 0px 3px rgb(0, 255, 157, 1));
  }

  li::before {
    content: '';
    position: absolute;
    bottom: -17px;
    left: 0;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background-color: rgb(0, 255, 157);
    transition: 0.3s;
    transform: scale(0);
    filter: drop-shadow(0px 0px 5px rgb(0, 255, 157, 1));
  }

  li:hover::after {
    width: 100%;
  }

  li:hover::before {
    transition-delay: 0.2s;
    left: calc(50% - 4px);
    transform: scale(1);
  }

  .selected::after {
    width: 100%;
  }

  .selected::before {
    transition-delay: 0.2s;
    left: calc(50% - 4px);
    transform: scale(1);
  }

  a {
    color: white;
    text-decoration: none;
  }
</style>
