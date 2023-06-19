<script lang="ts">
  import PlaceholderImage from "./PlaceholderImage.svelte";
  export let title: string;
  export let date: string;
</script>

<div class="card-container">
  <div class="image-container">
    <PlaceholderImage />
  </div>
  <div class="metadata-container">
    <span class="title">{title}</span>
    <span>{date}</span>
  </div>
</div>

<style lang="scss">
  * {
    font-family: "Inter";
  }

  .card-container {
    display: flex;
    position: relative;
    background-color: #A1CCA5;
    border: 1px solid black;
    border-radius: 0.5rem;
    left: 0;
    transition: left ease-out 0.2s;
    margin-right: 2rem;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;

    &:hover {
      left: 30px;
      transition: left ease-in 0.2s;
    }

    .image-container {
      display: flex;
      align-items: center;
      flex: 0.4 1 0;
    }

    .metadata-container {
      display: flex;
      flex-direction:column;
      flex: 0.6 1 0;
      margin: 1rem;

      .title {
        font-weight: 600;
        font-size: 1.1rem;
      }
    }
  }
</style>