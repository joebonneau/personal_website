<script lang="ts">
  import RecentPostCard from "./RecentPostCard.svelte";

  import "$lib/fonts.css";
  type RecentPost = {
    title: string;
    date: string;
    // image?: any //TODO: figure out correct type
  };
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
  <span><h1>Recent Posts</h1></span>
  {#each recentPosts as { title, date }}
    <RecentPostCard {title} {date} />
  {/each}
</div>

<style lang="scss">
  .recent-posts-container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin: 0 1.5rem;
  }

  span {
    display: flex;
    justify-content: center;
    h1 {
      font-weight: 800;
      font-size: 2rem;
    }
  }
</style>
