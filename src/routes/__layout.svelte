<script context="module">
  export const load = async ({ url }) => ({
    props: {
      key: url,
    },
  });
</script>

<script>
  import "$styles/app.pcss";
  import Nav from "$lib/Nav.svelte";
  import PageTransition from "$lib/PageTransition.svelte";
  import { page } from "$app/stores";
  export let key;
</script>

<Nav segment={$page.url} />
<main>
  <PageTransition refresh={$page.url}>
    <slot />
  </PageTransition>
</main>
