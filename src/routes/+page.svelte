<script>
  import Image from "$lib/components/Image.svelte";
  import Title from "$lib/components/Title.svelte";
</script>

<main class="container mx-auto pb-10">
  <section style="height:400px">
    <Image FORMATS="jpg" src="hero.jpg" />
  </section>
  <Title content="JPG" />
  <section class="grid md:grid-cols-3 lg:grid-cols-4 gap-x-5 md:gap-y-7">
    {#each [...Array(16).keys()] as n}
      <Image FORMATS="jpg" src="{n}.jpg" />
    {/each}
  </section>
</main>
