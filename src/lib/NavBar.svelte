<script lang="ts">
  import NavLink from "./NavLink.svelte";
  import GithubIcon from "./GithubIcon.svelte";
  import LinkedInIcon from "./LinkedInIcon.svelte";
  import type { Route } from "./types";

  export let menuOptions: Route[] = [];
</script>

<div class="navbar-container">
  <div class="left-nav">
    <a
      href="https://www.github.com/joebonneau"
      target="_blank"
      rel="noreferrer"
    >
      <span><GithubIcon /></span>
    </a>
    <a
      href="https://www.linkedin.com/in/joebonneau"
      target="_blank"
      rel="noreferrer"
    >
      <span><LinkedInIcon /></span>
    </a>
  </div>
  <div class="center-nav" />
  <div class="right-nav">
    {#each menuOptions as { name, path, element }}
      <NavLink {path} text={name} {element} />
    {/each}
  </div>
</div>

<style lang="scss">
  div.navbar-container {
    display: flex;
    height: 50px;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 10;
    background-color: #4f646f;

    .left-nav {
      display: flex;
      gap: 1.5rem;
      flex: 1.3 1 0;
      margin-left: clamp(100px, 16rem, 10svw);
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
