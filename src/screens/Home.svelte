<script>
  import { link, useLocation, useNavigate } from 'svelte-navigator'

  export let location = useLocation()
  export let navigate = useNavigate()
</script>

<div class="bg">
  <div class="glass" />
  <img
    src="https://png.pngtree.com/background/20210709/original/pngtree-colorful-background-picture-image_507712.jpg"
    alt="background pngtree.com"
  />
</div>

<style>
  .bg {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    min-height: 100vh;
  }
  img {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
  }
  .glass {
    width: 100%;
    height: 100vh;
    background-color: rgba(2, 7, 16, 0.93);
    backdrop-filter: blur(50px);
    position: relative;
    z-index: 1;
  }
</style>
