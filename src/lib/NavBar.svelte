<script lang="ts">
  // import sticky from "./sticky.js"
  import User from "./user-solid.svelte"
  import NavLink from "./NavLink.svelte";
  import GithubIcon from "./GithubIcon.svelte";
  import LinkedInIcon from "./LinkedInIcon.svelte";

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
      <!-- TODO: align to body of page, animate icons, make links -->
      <span><GithubIcon /></span>
      <span><LinkedInIcon /></span>
  </div>
  <div class="center-nav">
    
    {#each menuOptions as [name, route]}
      <NavLink path={route} text={name} />
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
    padding-top: 0.5rem;
    align-items: center;
    position: sticky;
    background-color: #4F646F;

    .left-nav {
      display: flex;
      gap: 1.5rem;
      flex: 1.3 1 0;
      justify-content: end;
      align-content: center;
    }

    .center-nav {
      display: flex;
      flex: 2 0 0;
      margin-right: 8rem;
      justify-content: end;
    }

    .right-nav {
      display: flex;
      flex: 0.6 1 0;
      justify-content: end;
    }
  }

  span {
    width: 25px;
    height: 25px;
  }

</style>