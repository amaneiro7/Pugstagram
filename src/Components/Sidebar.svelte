<script>
  import Footer from "./Footer.svelte";
  import Profile from "./Profile.svelte";
  import Stories from "./Stories.svelte";

  export let nickname
  export let name

</script>
<aside class="Sidebar">
    <div class="Sidebar-container">
        <Profile {nickname} {name}/>
        <Stories />
        <Footer />
    </div>
</aside>

<style>
  .Sidebar {
    position: relative;
    padding: 6rem 0 0 0;
  }
  .Sidebar-container {
    position: fixed;
  }
</style>