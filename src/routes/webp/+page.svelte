<script>
  import Image from "$lib/components/Image.svelte";
  import Title from "$lib/components/Title.svelte";
</script>

<main class="container mx-auto pb-10">
  <section style="height:400px">
    <Image FORMATS="webp" src="hero.jpg" />
  </section>
  <Title content="WEBP" />
  <section class="grid md:grid-cols-3 lg:grid-cols-4 gap-x-5 md:gap-y-7">
    {#each [...Array(16).keys()] as n}
      <Image FORMATS="webp" src="{n}.jpg" />
    {/each}
  </section>
</main>
