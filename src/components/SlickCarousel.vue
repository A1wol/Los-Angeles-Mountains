<template>
  <div>
    <VueSlickCarousel
      :slidesToScroll="4"
      :slidesToShow="4"
      :responsive="responsiveSettings"
      :arrows="false"
      :dots="true"
    >
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image1.png" alt="Carousel image" />
      </div>
      <div class="carousel-slide">
        <img src="..\..\src\assets\carousel-image2.png" alt="Carousel image" />
      </div>
    </VueSlickCarousel>
  </div>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  components: { VueSlickCarousel },
  data: function () {
    return {
      responsiveSettings: [
        {
          breakpoint: 1324,
          settings: {
            slidesToShow: 3,
            slidesToScroll: 3,
            infinite: true,
            dots: true,
          },
        },
        {
          breakpoint: 1100,
          settings: {
            slidesToShow: 2,
            slidesToScroll: 2,
            initialSlide: 2,
          },
        },
        {
          breakpoint: 680,
          settings: {
            slidesToShow: 1,
            slidesToScroll: 1,
          },
        },
      ],
    };
  },
};
</script>

<style>
.slick-slide {
  width: 70%;
}
.slick-slider {
  background-color: #344159cf;
  padding: 0 20%;
}
.carousel-slide {
  display: flex;
  gap: 12px;
}

@media screen and (max-width: 1444px) {
  .slick-slider {
    padding: 0 5%;
  }
}
</style>
