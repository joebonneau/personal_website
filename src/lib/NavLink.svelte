<script lang="ts">
  import { goto } from "$app/navigation"
  export let path: string;
  export let text: string;
  import "./fonts.css"
</script>

{#if text === "Home"}
  <a href={path} rel="noreferrer">
    {text}
  </a>
{:else}
  <!-- TODO: route to sections -->
  <a href={path} rel="noreferrer">
    {text}
  </a>
{/if}

<style lang="scss">
  a {
    display: block;
    font-family: "Roboto Mono";
    color: #000;
    text-decoration: none;
    font-weight: 500;
    padding: 0 1rem;
    transform: translateY(0);
    transition: color, transform 0.2s ease-out;

    &:hover {
      color: #D17B0F;
      transform: translateY(-5%);
      transition: color, transform 0.2s ease-in;
    }
  }
</style>