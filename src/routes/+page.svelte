<script lang="ts">
  import { onDestroy, onMount } from "svelte";
  import NavBar from "../lib/NavBar.svelte";
  import type { Route } from "$lib/types";
  import "../lib/fonts.css";

  let top: Element;
  let one: Element;
  let two: Element;
  let three: Element;
  let four: Element;
  let about: Element;
  let experience: Element;
  let menuOptions: Route[];

  let observers: IntersectionObserver[] = [];
  onMount(() => {
    const sectionsArray: Element[] = [
      top,
      one,
      two,
      three,
      four,
      about,
      experience,
    ];
    sectionsArray.forEach((el) => {
      const observer = new IntersectionObserver((entries, observer) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.remove("hidden");
            entry.target.classList.add("show");
            // only observe until first intersection, then stop
            observer.unobserve(entry.target);
          } else {
            entry.target.classList.remove("show");
            entry.target.classList.add("hidden");
          }
        });
      });
      observers.push(observer);
      observer.observe(el);
    });

    // await tick();
    menuOptions = [
      { name: "Home", path: "/", element: top },
      { name: "About", path: "#about", element: about },
      { name: "Experience", path: "#experience", element: experience },
      { name: "Blog", path: "blog", element: null },
    ];
  });

  onDestroy(() => {
    observers?.forEach((observer) => {
      if (typeof observer !== "undefined") {
        observer.disconnect();
      }
    });
  });
</script>

<NavBar {menuOptions} />

<section bind:this={top} id="top">
  <h1 class="hidden" bind:this={one}>Hi, my name is</h1>
  <h2 class="hidden" bind:this={two}>Joe Bonneau.</h2>
  <h3 class="hidden" bind:this={three}>I'm a full-stack software engineer.</h3>
  <div>
    <p class="hidden" bind:this={four}>
      I primarily build web applications and do it all - from writing REST APIs
      to building interfaces. I don't often independently design them, though I
      find it fascinating and am actively working at improving in that area.
    </p>
  </div>
</section>

<section bind:this={about} id="about">
  <img src="../dummy_300x300.png" alt="Joe Bonneau" />
</section>

<section id="experience" class="hidden" bind:this={experience}>
  <h1>more stuff</h1>
</section>

<style lang="scss">
  div {
    // TODO: use clamp for better scaling
    max-width: 35vw;
  }

  p {
    font-size: 1rem;
    font-weight: 600;
  }

  * {
    font-family: "Inter";
  }

  h1 {
    font-size: 1rem;
    font-weight: 500;
    color: #d17b0f;
    font-family: "Roboto Mono";
    margin-bottom: 0.5rem;

    &.hidden {
      opacity: 0;
      filter: blur(5px);
      transition: all ease-in 0.25s;
      transition-property: opacity, filter;
    }
  }

  h2 {
    font-size: 4rem;
    margin-top: 0;
    margin-bottom: 0;

    &.hidden {
      opacity: 0;
      filter: blur(5px);
      transition: all ease-in 3s;
      transition-property: opacity, filter;
    }
  }

  h3 {
    font-size: 3rem;
    margin-top: 0;
    margin-bottom: 0;
    color: #dee7e7;
    &.hidden {
      opacity: 0;
      filter: blur(5px);
      transition: all ease-in 2s;
      transition-property: opacity, filter, transform;
    }
  }

  p {
    font-weight: 400;
    color: #dee7e7;

    &.hidden {
      opacity: 0;
      filter: blur(5px);
      transform: translateX(-100%);
      transition: all ease-in 2.5s;
      transition-property: opacity, filter, transform;
    }
  }

  :global(.show) {
    opacity: 1;
    filter: blur(0);
    transform: translateX(0);
    transition: all ease-in 1.1s;
    transition-property: opacity, filter, transform;
  }

  section {
    display: grid;
    place-items: start;
    align-content: start;
    min-height: 100svh;
    margin-top: 8em;
    margin-left: clamp(100px, 16rem, 10svw);

    // &.hidden {
    //   opacity: 0;
    //   filter: blur(5px);
    //   transform: translateX(-100%);
    //   transition: all ease-in 0.75s;
    //   transition-property: opacity, filter, transform;
    // }
  }
</style>
