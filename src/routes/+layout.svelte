<script>
    import "../app.css";
    import Nav from './nav.svelte';
    import Footer from "./footer.svelte";
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
</svelte:head>

<Nav />

<slot />

<Footer />
