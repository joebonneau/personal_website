<script lang="ts">
  import { goto } from "$app/navigation"
  export let path: string;
  export let text: string;
  import "./fonts.css"
</script>

<div>
  <button on:click={() => goto(path)}>
    {text}
  </button>
</div>

<style lang="scss">

* {
    font-family: "Roboto Mono";
  }
  div {
    background-color: inherit;
  }
  button {
    border: none;
    color: #000;
    font-weight: 500;
    font-size: 1rem;
    padding: 0.5rem 1rem;
    background-color: inherit;
    transform: translateY(0);
    transition: color, transform 0.2s ease-out;
    
  }

  button:hover {
    color: #D17B0F;
    transform: translateY(-5%);
    transition: color, transform 0.20s ease-in;
    cursor: pointer;
  }
</style>