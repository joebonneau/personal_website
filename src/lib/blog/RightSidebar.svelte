<script lang="ts">
  import RecentPostCard from "./RecentPostCard.svelte";
  
  import "$lib/fonts.css"
    type RecentPost = {
        title: string
        date: string
        // image?: any //TODO: figure out correct type 
    }
    export let recentPosts: RecentPost[] = [
      {
        title: "Recent Post 1",
        date: "2023-01-01",
      },
      {
        title: "Recent Post 2 with longer name",
        date: "2023-02-02",
      },
      {
        title: "Recent Post 3 with even longer name wowwwwwww",
        date: "2023-03-03",
      },
    ];
</script>

<div class="recent-posts-container">
  {#each recentPosts as { title, date }}
    <RecentPostCard {title} {date} />
  {/each}
</div>

<style>
  .recent-posts-container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin: 0 1.5rem;
  }
</style>