<script>
  import NavBar from "$lib/NavBar.svelte";
  import LeftSidebar from "$lib/blog/LeftSidebar.svelte";
  import RightSidebar from "$lib/blog/RightSidebar.svelte";
  import "../../lib/fonts.css"
</script>

<NavBar />
<div class="outer-container">
    <div class="left-sidebar">
        <LeftSidebar />
    </div>
    <div class="middle">
        <p class="blog-title">Post Title</p>
        <p class="author-metadata">Author: Joe Bonneau</p>
        <p class="date-metadata">June 16, 2023</p>
        <p class="post-body">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ad, consectetur. Repellendus dolorum, iure corporis doloremque porro fuga quam odio ipsa. Dignissimos sed omnis illo illum et vero, harum doloremque libero.
          Ea numquam reprehenderit voluptates! Adipisci eveniet officiis quod nihil qui iste fugiat nesciunt deleniti. Tenetur voluptate maiores corporis, doloremque nesciunt odio mollitia minima quibusdam at, commodi qui fugiat id optio?
          Ab commodi doloremque vel, amet asperiores accusantium quaerat quo incidunt nam eveniet eligendi quod soluta sint illum dolore voluptatum enim iusto, libero omnis velit eius, porro vero doloribus ipsa? Assumenda?
          Earum, distinctio ipsam et fugit fuga doloribus natus molestiae saepe quibusdam optio inventore magni non sunt possimus deserunt voluptatum illum reprehenderit provident maxime repudiandae laudantium. Enim suscipit nam dolores illo.
          Accusamus, repellendus vel vero eligendi debitis aliquam provident officiis eos soluta excepturi quae inventore assumenda! Quos odio explicabo sint nesciunt consequatur laborum quis deserunt ullam? Eum, in laborum? Obcaecati, ipsa.
          Architecto officiis voluptatum error, animi vitae vel. Blanditiis deserunt quod a, debitis reiciendis in recusandae quia pariatur unde, corporis magni modi atque officiis asperiores esse cumque similique maxime? Molestias, ut!
          Omnis esse architecto molestias dicta distinctio cum, tempore eligendi excepturi veniam culpa! Soluta ut facere iure deleniti, asperiores quibusdam? Dolorem maxime sed assumenda laborum praesentium. Deserunt reprehenderit dolorem hic mollitia?
          Suscipit quas quibusdam aliquid, consequuntur ullam blanditiis nam soluta? Odio, provident ex tempora excepturi porro aliquid, delectus, reiciendis ab facere harum magni corporis dolorum minus blanditiis voluptas? Quos, dicta architecto?
          Incidunt voluptatibus repellendus quaerat quo quis quas doloribus error sint facere omnis provident vel voluptas architecto atque nam soluta dolorem tempora assumenda in laborum, harum maiores enim voluptatem. Odio, ducimus!
          Laborum fugit magnam officiis illo dolore facilis quo tempora odio hic ipsam, eaque qui amet quam mollitia, est quae? Sequi dignissimos dolorem perspiciatis aspernatur fugiat aliquam accusamus inventore labore soluta?
        </p>
    </div>
    <div class="right-sidebar">
      <RightSidebar />
    </div>
</div>

<style lang="scss">

    * {
        font-family: "Inter";
    }

    .outer-container {
      margin: 1rem 2rem 0 2rem;
      display: flex;
      flex-direction: row;
    }

    .right-sidebar {
      display: flex;
      flex-direction: column;
    }

    .left-sidebar {
      flex: 0.2 1 0;
    }

    .right-sidebar {
      flex: 0.3 1 0;
      padding-right: 10rem;
    }

    .middle {
      border-color:aliceblue;
      background-color: #A1CCA5;
      border-radius: 0.25rem;
      border-left: 1px;
      border-right: 1px;
      height: 100%;
      flex: 0.4 1 0;
      padding: 0 1rem;
      text-align: justify;
      // max-height: calc(100vh - 100px);
      overflow: auto;
      // TODO: revisit
      // position: relative;
      // z-index: 10;
      // box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;

        .blog-title {
          font-weight: 800;
          font-size: 2.5rem;
          margin-bottom: 0.5rem;
        }

        .author-metadata {
          font-weight: 600;
          font-size: 1.25rem;
          margin-bottom: 0.25rem;
        }

        .date-metadata {
          font-weight: 400;
          font-size: 1rem;
          margin-top: 0.25rem;
        }

        .post-body {
          line-height: 1.75;
        }
    }
</style>
