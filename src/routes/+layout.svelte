<script>
  import "../app.postcss";
</script>

<svelte:head>
	<title>Image Optim - Svelte example</title>
</svelte:head>


<div class="container mx-auto my-4">
  <nav class="px-4 flex gap-8 font-thin font-mono">
    <a href="/">JPG</a>
    <a href="/webp">WEBP</a>
    <a href="/avif">AVIF</a>
    <a href="https://github.com/ohbob/image-optim"><img style="height:20px" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt=""></a>

  </nav>
</div>
<slot />

<style>
a {
  color: transparent;
  text-shadow: 0 0 0 #165ea5;
}


</style>
