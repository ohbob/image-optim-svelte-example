<script>
  import Image from '$lib/components/Image.svelte'
  import Title from '$lib/components/Title.svelte'
  const FORMATS = ['webp', 'jpg']
</script>

<main class="container mx-auto pb-10">
  <section style="height:400px" fetchpriority="high">
    <Image {FORMATS} src="hero.jpg" lazyload="eager" fetchprior="high" />
  </section>
  <Title content="WEBP" />
  <section class="grid md:grid-cols-3 lg:grid-cols-4 gap-x-5 md:gap-y-7">
    {#each [...Array(16).keys()] as n}
      <Image {FORMATS} src="{n}.jpg" />
    {/each}
  </section>
</main>
