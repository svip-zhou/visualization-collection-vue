<script setup lang="ts">
import cartoonFigure from "images/html/cartoonFigure.png";
</script>

<template>
  <div style="width: 100%">
    <div class="container">
      <img :src="cartoonFigure" alt="" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  width: 100%;
  height: 450px;
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    $s: 280px;
    /* image size */
    $b: 5px;
    /* border thickness */
    $c: #c02942;
    /* border color */
    --f: 1;
    /* initial scale */

    $g: 50% / calc(100% / var(--f)) 100% no-repeat content-box;
    $o: calc((1 / var(--f) - 1) * $s / 2 - $b);

    width: $s;
    aspect-ratio: 1;
    padding-top: calc($s / 5);
    cursor: pointer;
    border-radius: 0 0 calc($s / 2) calc($s / 2);
    outline: $b solid $c;
    outline-offset: $o;
    background: radial-gradient(circle closest-side,
        #ecd078 calc(99% - $b),
        $c calc(100% - $b) 99%,
        #0000) $g;
    -webkit-mask: linear-gradient(#000 0 0) no-repeat 50% calc(-1 * $o) / calc(100% / var(--f) - 2 * $b) 50%,
      radial-gradient(circle closest-side, #000 99%, #0000) $g;
    transform: scale(var(--f));
    transition: 0.5s;

    &:hover {
      --f: 1.3;
      /* hover scale */
    }
  }
}
</style>
