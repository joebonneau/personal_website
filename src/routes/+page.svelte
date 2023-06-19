<script lang="ts">
  import { onDestroy, onMount } from "svelte";
  import NavBar from "../lib/NavBar.svelte";
  import { fade } from "svelte/transition";
  import "../lib/fonts.css"

  const sectionsArray: Element[] = [];
  let observers: IntersectionObserver[] = [];
  onMount(() => {
    sectionsArray.forEach((el) => {
      const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
          console.log(entry);
          if (entry.isIntersecting) {
            entry.target.classList.remove("hidden")
            entry.target.classList.add("show");
            console.log(entry.target.classList)
          } else {
            entry.target.classList.remove("show");
            entry.target.classList.add("hidden")
          }
        })
      });
      observers.push(observer);
      observer.observe(el)
    });
  })

  onDestroy(() => {
    observers?.forEach((observer) => {
      if (typeof observer !== "undefined") {
        observer.disconnect()
      }
    })
  })
  
</script>

<NavBar />

<section class="hidden" bind:this={sectionsArray[0]}>
  <div >
    <p>Hi, my name is Joe Bonneau</p>
  </div>
</section>

<section class="hiddenr" bind:this={sectionsArray[1]}>
  <h1>more stuff</h1>
</section>

<style lang="scss">
  div {
    // overflow: auto;
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

  section {
    display: grid;
    place-items: center;
    align-content: center;
    min-height: 125vh;
    
    &:global(.hidden) {
      opacity: 0;
      filter: blur(5px);
      transform: translateX(-100%);
      transition: all ease-in 0.75s;
      transition-property: opacity, filter, transform;
    }

    &:global(.show) {
      opacity: 1;
      filter: blur(0);
      transform: translateX(0);
      transition: all ease-in 0.75s;
      transition-property: opacity, filter, transform;
    }
  }
  

  
</style>