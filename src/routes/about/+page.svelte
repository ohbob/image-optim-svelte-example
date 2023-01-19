


<div class="container mx-auto">

<p class="text-lg">a) Prepare images</p>
<p class="">
    docker run <br>-v ~/Documents/GitHub/image-optim-svelte-example/static:/app/input <br>-v ~/Documents/GitHub/image-optim-svelte-example/static/optim:/app/output <br>-e SIZES="thumb, 50, small, 200, medium, 400, large, 720, xl, 920, xxl, 1920" <br>-e FORMATS="webp, avif, jpg" <br>ghcr.io/ohbob/image-optim:latest
</p>

<img src="" alt="">

</div>
