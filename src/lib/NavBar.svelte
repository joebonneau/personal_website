<script lang="ts">
  // import sticky from "./sticky.js"
  import User from "./user-solid.svelte"
  import NavLink from "./NavLink.svelte";

  // export let stickToTop = true;
  // let isStuck = false;

  // function handleStuck(e: CustomEvent) {
  //   isStuck = e.detail.isStuck;
  // }

  const menuOptions = [
    ["Home", "/"],
    ["About", "/about"],
    ["Experience", "/experience"],
    ["Blog", "/blog"],
  ];
</script>

<div 
  class="navbar-container"
>
  <div class="left-nav">
    <!-- <User /> -->
      <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-45.7 48C79.8 304 0 383.8 0 482.3C0 498.7 13.3 512 29.7 512H418.3c16.4 0 29.7-13.3 29.7-29.7C448 383.8 368.2 304 269.7 304H178.3z"/></svg>
  </div>
  <div class="center-nav">
    {#each menuOptions as [name, route]}
      <NavLink path={route} text={name.toUpperCase()} />
    {/each}
  </div>
  <div class="right-nav">
    <!-- {#each menuOptions as [name, route]}
      <NavLink path={route} text={name.toUpperCase()} />
    {/each} -->
  </div>
</div>

<style lang="scss">
  div.navbar-container {
    display: flex;
    position: sticky;
    background-color: #415D43;

    .left-nav {
      display: flex;
      flex: 1.3 1 0;
      justify-content: start;
    }

    .center-nav {
      display: flex;
      flex: 2 0 0;
      justify-content: end;
    }

    .right-nav {
      display: flex;
      flex: 0.6 1 0;
      justify-content: end;
    }
  }

</style>