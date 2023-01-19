<script>
  export let w = "100%";
  export let src = "";
  export let alt = "Image";
  src = src.split(".")[0];
  let containerWidth;
  export let fetchprior="low"
  export let lazyload = "lazy"
  export let SIZES = {
    thumb: 50,
    small: 100,
    medium: 200,
    large: 350,
    xl: 720,
    xxl: 920,
  };

  export let OUTPUT = "optim";
  export let FORMATS = ["jpg", "webp", "avif"];

  function getImageSrc(src, imageFormat, maxSize) {
    let str = "";
    for (const [name, width] of Object.entries(SIZES)) {
      if (width <= maxSize.containerWidth) {
        str += `${OUTPUT}/${name}_${src.src}.${imageFormat} ${width}w, `;
      }
    }
    return str;
  }
</script>

<div style="width: 100%; max-width:{w};">
  <div style="overflow: hidden;" bind:offsetWidth={containerWidth}>
    <picture>
      {#if FORMATS.includes("avif")}
        <source
          type="image/avif"
          srcSet={getImageSrc({ src }, "avif", { containerWidth })}
        />
      {/if}
      {#if FORMATS.includes("webp")}
        <source
          type="image/webp"
          srcSet={getImageSrc({ src }, "webp", { containerWidth })}
        />
      {/if}
      {#if FORMATS.includes("jpg")}
        <source srcSet={getImageSrc({ src }, "jpg", { containerWidth })} />
      {/if}

      {#if FORMATS.includes("webp")}
         <img fetchpriority={fetchprior} {alt} src="{OUTPUT}/thumb_{src}.webp" loading={lazyload} />
         {:else}
          <img fetchpriority={fetchprior} {alt} src="{OUTPUT}/thumb_{src}.jpg" loading={lazyload} />
      {/if}

    </picture>
  </div>
</div>

<style>
  img,
  div {
    background: rgb(212, 211, 211);
    object-position: center;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
</style>
