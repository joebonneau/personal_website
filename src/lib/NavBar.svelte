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
    ["About", "#about"],
    ["Experience", "#experience"],
    ["Blog", "#blog"],
  ];
</script>

<div class="navbar-container">
  <div class="left-nav">
    <!-- TODO: align to body of page, animate icons, make links -->
    <a href="https://www.github.com/joebonneau" target="_blank" rel="noreferrer">
      <span><GithubIcon /></span>
    </a>
    <a href="https://www.linkedin.com/in/joebonneau" target="_blank" rel="noreferrer">
      <span><LinkedInIcon /></span>
    </a>
  </div>
  <div class="center-nav">
    
    <!-- {#each menuOptions as [name, route]}
      <NavLink path={route} text={name} />
    {/each} -->
  </div>
  <div class="right-nav">
    {#each menuOptions as [name, route]}
      <NavLink path={route} text={name} />
    {/each}
  </div>
</div>

<style lang="scss">

  div.navbar-container {
    display: flex;
    padding: 0.75rem 0;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 10;
    background-color: #4F646F;

    .left-nav {
      display: flex;
      gap: 1.5rem;
      flex: 1.3 1 0;
      margin-left: 16rem;
      justify-content: start;
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
      margin-right: 16rem;
      justify-content: end;
    }
  }

  span {
    max-width: 25px;
    max-height: 25px;
  }

</style>