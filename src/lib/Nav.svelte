<script>
    export let segment;
</script>

<div class="nav">
  <a href="/" class='{segment === undefined ? "current" : ""}'>Home</a>
  <a href="/checkmark" class='{segment === "about" ? "current" : ""}'>checkmark</a>
  <a href="/cooltext" class='{segment === "about" ? "current" : ""}'>cooltext</a>
</div>

<style lang="postcss">
  @import "variables.pcss";

  .nav {
    display: flex;
    justify-content: center;
  }

  .current {
    text-decoration: underline;
  }

  a {
    padding: 20px;
    background-color: #ffb3b3;
  }
</style>