<script>
  import NavBar from "../lib/NavBar.svelte";
  import "../lib/fonts.css"
</script>

<NavBar />

<style>
  div {
    overflow: auto;
    /* margin-top: 0; */
    margin: 0 6rem;
    height: calc(100vh - 30px);
  }

  p {
    font-size: 4rem;
    font-weight: 600;
  }

  * {
    font-family: "Inter";
  }
  /* @font-face {
    font-family: 'Inter';
    font-style:  normal;
    font-weight: 100;
    font-display: swap;
    src: url("%sveltekit.static%/Inter-Thin.woff2?v=3.19") format("woff2"),
         url("%sveltekit.static%/Inter-Thin.woff?v=3.19") format("woff");
  } */
</style>

<div>
  <p>Hi, my name is Joe Bonneau</p>
</div>
