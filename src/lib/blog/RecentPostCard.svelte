<script lang="ts">
  import PlaceholderImage from "$lib/dummy_180x120.svelte"
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
    background-color: #A1CCA5;
    border: 1px solid black;
    border-radius: 0.5rem;

    .image-container {
      flex: 0.4 1 0;
    }

    .metadata-container {
      display: flex;
      flex-direction:column;
      flex: 0.6 1 0;
      margin-top: 1rem;
      margin-left: 1rem;

      .title {
        font-weight: 600;
        font-size: 1.1rem;
      }
    }
  }
</style>