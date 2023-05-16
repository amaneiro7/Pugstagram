<script>  
  import { onMount } from "svelte";
  import Header from "./Components/Header.svelte";
  import Main from "./Components/Main.svelte";
  import Sidebar from "./Components/Sidebar.svelte";
  import Timeline from "./Components/Timeline.svelte";
  let data = {}
  const API = "https://kittygram-api.vercel.app/"
  onMount(async () => {
    const response = await fetch(API)
    data = await response.json()
    console.log(await data)
  })
  
</script>

<style>
  @import url(https://fonts.googleapis.com/css?family=Lato:100,100italic,300,300italic,regular,italic,700,700italic,900,900italic);
  @import url(https://fonts.googleapis.com/css?family=Pacifico:regular);
  :global(:root) {
    background-color: #676778;
    color: rgba(38, 38, 38, 0.7);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;  
  }
  
</style>

<Header />
<Main>
  <Timeline posts={data.posts}/>
  <Sidebar {...data.user} />
</Main>
