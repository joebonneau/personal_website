<script lang="ts">
  export let path: string;
  export let text: string;
  export let element: Element | null;
  import "./fonts.css";

  const scrollIntoViewWithOffset = (element: Element, offset: number = 50) => {
    window.scrollTo({
      behavior: "smooth",
      top:
        element.getBoundingClientRect().top -
        document.body.getBoundingClientRect().top -
        offset,
    });
  };

  const onClick = (e: Event) => {
    console.log({ element });
    e.preventDefault();
    if (element !== null) {
      // element.scrollIntoView({ behavior: "smooth", block: "start", inline: "nearest" });
      scrollIntoViewWithOffset(element);
    }
  };
</script>

{#if element !== null}
  {#if path === "/" && document.URL.includes("blog")}
    <a href={path} rel="noreferrer">
      {text}
    </a>
  {:else}
    <button on:click={onClick}>{text}</button>
  {/if}
{:else}
  <a href={path} rel="noreferrer">
    {text}
  </a>
{/if}

<style lang="scss">
  * {
    font-family: "Roboto Mono";
  }

  button {
    background-color: inherit;
    border: none;
  }

  a,
  button {
    color: #000;
    text-decoration: none;
    font-weight: 500;
    font-size: 1rem;
    padding: 0 1rem;
    transform: translateY(0);
    transition: color, transform 0.2s ease-out;

    &:hover {
      color: #d17b0f;
      transform: translateY(-5%);
      transition: color, transform 0.2s ease-in;
      cursor: pointer;
    }
  }
</style>
