<script>
  import GithubIcon from "$lib/GithubIcon.svelte";
  import LinkedInIcon from "$lib/LinkedInIcon.svelte";
</script>

<div>
  <ul>
    <li>
      <a
        href="https://www.github.com/joebonneau"
        aria-label="GitHub"
        target="_blank"
        rel="noreferrer"
      >
        <GithubIcon />
      </a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/joebonneau"
        aria-label="LinkedIn"
        target="_blank"
        rel="noreferrer"
      >
        <LinkedInIcon />
      </a>
    </li>
  </ul>
</div>

<style lang="scss">
  ul {
    display: flex;
    flex-direction: column;
    -webkit-box-align: center;
    gap: 20px;
    align-items: center;
    margin: 0px;
    padding: 0px;
    list-style: none;
    z-index: 10;
  }

  li {
    width: 35px;
    height: 35px;

    &:last-of-type {
      margin-bottom: 20px;

      ::after {
        position: fixed;
        bottom: 0;
        content: "";
        display: block;
        width: 1px;
        height: 90px;
        margin: 0px auto;
        background-color: white;
      }
    }

    a {
      padding: 10px;
    }
  }
  div {
    display: block;
    width: 40px;
    position: fixed;
    bottom: 0px;
    left: 40px;
    right: auto;
    z-index: 10;
  }
</style>
