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
  div {
    background-color: inherit;
  }
  button {
    border: none;
    color: white;
    font-weight: 600;
    font-size: 1.25rem;
    padding: 0.5rem 1rem;
    background-color: inherit;
    // background-color: #709775; 
  }

  button:hover {
    background-color: #709775;
    transition: background-color 0.15s ease-in-out;
    cursor: pointer;
  }
</style>