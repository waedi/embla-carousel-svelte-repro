<script lang="ts">
  import emblaCarouselSvelte from "embla-carousel-svelte";
  import type { EmblaOptionsType, EmblaCarouselType } from "embla-carousel";

  let emblaApi;
  let options: EmblaOptionsType = { loop: false };

  function onInit(event: CustomEvent<EmblaCarouselType>) {
    emblaApi = event.detail;
    console.log(emblaApi.slideNodes());
  }
</script>

<div class="embla" use:emblaCarouselSvelte={{ options }} onemblaInit={onInit}>
  <div class="embla__container">
    <div class="embla__slide">Slide 1</div>
    <div class="embla__slide">Slide 2</div>
    <div class="embla__slide">Slide 3</div>
  </div>
</div>

<style>
  .embla {
    overflow: hidden;
  }
  .embla__container {
    display: flex;
  }
  .embla__slide {
    flex: 0 0 100%;
    min-width: 0;
  }
</style>
