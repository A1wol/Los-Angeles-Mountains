<template>
  <div id="app">
    <!-- First section -->
    <section class="hero-container">
      <div class="main-image">
        <img v-parallax="0.4" src="..\src\assets\hero-image.png" alt="Main Logo Image" />
      </div>

      <nav class="container" style="position: absolute">
        <div>
          <img src="..\src\assets\nav-logo.png" alt="Logo" />
        </div>

        <div class="navigation-links" style="color: white">
          <a href="#history-container">01. HISTORY</a>
          <a href="#climb-container">02. TEAM</a>
        </div>
      </nav>
    </section>

    <!-- First navigation bar - logo + links -->
    <section class="second-nav">
      <div class="container">
        <div>
          <img src="..\src\assets\text-logo.png" alt="Logo" />
        </div>
        <div class="navigation-links">
          <a href="#history-container">01. HISTORY</a>
          <a href="#climb-container">02. TEAM</a>
        </div>
      </div>
    </section>

    <!-- History section -->
    <section id="history-container">
      <div class="container">
        <div>
          <img src="..\src\assets\01-title.png" alt="Title" />
        </div>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
          incididunt ut labore et dolore magna aliqua. Tellus id interdum velit laoreet.
          Eu tincidunt tortor aliquam nulla facilisi cras fermentum odio. Felis imperdiet
          proin fermentum leo vel orci porta non. Diam in arcu cursus euismod quis
          viverra. Dignissim convallis aenean et tortor.
        </p>
      </div>

      <slick-carousel />
    </section>

    <section id="climb-container">
      <div class="container">
        <div>
          <img src="..\src\assets\02-title.png" alt="Number" />
        </div>

        <p>
          Congue nisi vitae suscipit tellus mauris a diam maecenas sed. Proin sed libero
          enim sed faucibus. Adipiscing commodo elit at imperdiet dui accumsan.
        </p>
      </div>
    </section>

    <!-- Tabs -->
    <section class="mountain-container">
      <div class="select-container">
        <div>
          <span
            class="tab"
            :class="[chosenComp === 1 ? 'chosen' : '']"
            @click="chosenComp = 1"
            >Mountain 1
          </span>

          <span
            class="tab"
            :class="[chosenComp === 2 ? 'chosen' : '']"
            @click="chosenComp = 2"
            >Mountain 2
          </span>
        </div>
      </div>

      <div class="schedule-tabs" style="max-height: 510px; height: 510px">
        <Transition name="fade">
          <div key="1" style="max-height: 510px" v-if="chosenComp == 1">
            <div>
              <img
                class="schedule"
                src="..\src\assets\tab-2-schedule.png"
                alt="Schedule"
              />
            </div>
            <img
              class="background"
              src="..\src\assets\mountain-image1.png"
              alt="Background"
            />
          </div>
          <div key="2" style="max-height: 510px" v-else-if="chosenComp == 2">
            <div>
              <img
                class="schedule"
                src="..\src\assets\tab-1-schedule.png"
                alt="Schedule"
              />
            </div>
            <img
              class="background"
              src="..\src\assets\mountain-image.png"
              alt="Background"
            />
          </div>
        </Transition>
      </div>
    </section>

    <!-- Mountain container -->
    <section class="mobile-mountain-container">
      <VSAccordion />
    </section>

    <!-- Footer -->
    <footer>
      <div>
        <div>
          <img src="..\src\assets\footer-logo.png" alt="Logo" />
        </div>

        <p>COPYRIGHT 2016. ALL RIGHTS RESERVED.</p>
      </div>
    </footer>
  </div>
</template>

<script>
// Imports
import SlickCarousel from "./components/SlickCarousel.vue";
import VSAccordion from "./components/VSAccordion.vue";

export default {
  name: "App",
  components: { SlickCarousel, VSAccordion },
  data: function () {
    return {
      chosenComp: 1,
    };
  },
};
</script>

<style>
/* Transition */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  height: 580px;
}

/* General app styles */
html {
  scroll-behavior: smooth;
}
body {
  margin: 0px;
}

.container {
  max-width: 900px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 16px;
}
.main-image {
  position: relative;
}
.main-image > img {
  object-position: 0 12px;
  margin-top: -24px;
}

.hero-container {
  height: 780px;
  padding-top: 8px;
  display: flex;
  background-position: center;
  justify-content: center;
  overflow: hidden;
}
.hero-container .mask-image {
  width: 100%;
}
.hero-container .mask-image-container img {
  position: absolute;
  left: 0;
  max-width: 100%;
  bottom: -35px;
}
.carousel-slide {
  display: flex !important;
  justify-content: center;
}
.navigation-links {
  display: flex;
  align-items: center;
  gap: 50px;
  font-size: 14px;
  height: 50px;
}
.second-nav {
  display: flex;
  justify-content: center;
  padding: 8px 0;
}

#history-container {
  background-image: url("..\src\assets\mid-photo.png");
  width: 100%;
  height: 860px;
  background-position: center;
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
#history-container .container:nth-child(2) {
  display: flex;
  justify-content: center;
  width: 100%;
}
#history-container .container p {
  padding: 0 63px;
  margin-top: -9px;
  font-size: 16px;
  color: #212529;
  line-height: 1.5;
  position: relative;
  margin-left: auto;
  margin-right: auto;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  max-width: 840px;
}
#history-container .container {
  justify-content: center;
  display: flex;
  position: relative;
  margin-left: auto;
  margin-right: auto;
  flex-direction: column;
  padding-top: 32px;
}

.second-nav a {
  color: #364659 !important;
}
.carousel-slide {
  padding-top: 15px;
}
#climb-container {
  display: flex;
  justify-content: center;
  padding: 16px 0;
}
.mountain-container {
  display: block;
}
.mobile-mountain-container {
  display: none;
}
.mountain-container .select-container > div .chosen {
  background-color: rgb(171, 171, 171) !important;
  color: #364659 !important;
  text-decoration: underline;
}
.mountain-container .select-container span {
  cursor: pointer;
  display: flex;
  align-items: center;
  padding: 0 16px;
}
.mountain-container .select-container {
  background-color: #364659;
  text-transform: uppercase;
  color: rgba(171, 171, 171, 1);
  font-size: 24px;
  font-family: "Mohave";
}
.mountain-container .select-container > div {
  max-width: 870px;
  display: flex;
  height: 40px;
  justify-content: center;
  width: 100%;
}
#climb-container p {
  max-width: 580px;
  margin: 10px 0;
  display: flex;
  align-items: center;
  font-size: 16px;
  color: #212529;
  line-height: 1.5;
  margin-bottom: 10px;
  position: relative;
  margin-left: auto;
  margin-right: auto;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
#climb-container .container {
  margin-left: 55px;
}
.navigation-links a {
  font-weight: 600;
  cursor: pointer;
  font-family: "Nunito Sans";
  font-style: italic;
  color: white;
  text-decoration: underline;
}
.slick-prev {
  color: black;
  left: 30px;
  z-index: 99;
}
.slick-next {
  color: black;
  right: 30px;
}
.slick-dots {
  position: static;
}
.slick-dots button::before {
  color: white !important;
  font-size: 10px !important;
}
.schedule-tabs {
  position: relative;
}
.schedule {
  position: absolute;
  left: 22%;
  top: 90px;
  max-width: 330px;
  z-index: 99;
}
.background {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
footer {
  display: flex;
  justify-content: center;
  background-color: #465573;
}
footer > div {
  display: flex;
  justify-content: space-between;
  max-width: 915px;
  width: 100%;
  color: #687da6;
  font-weight: 900;
  font-family: "Nunito Sans";
  font-style: italic;
  padding: 8px 0;
  font-size: 14px;
}

/* Responsive */
@media screen and (max-width: 1024px) {
  .navigation-links {
    flex-direction: column;
    gap: 0;
  }
  .container {
    padding: 0;
  }
  .schedule {
    left: 0;
    top: 0;
    max-width: 300px;
  }
  .background {
    min-height: 300px;
  }
  .hero-container {
    height: 500px;
  }
  .container > div {
    padding: 0 16px;
  }
  #history-container .container {
    padding: 16px 0;
  }
  #history-container .container p {
    padding: 16px;
  }
  .main-image > img {
    object-position: -30% 12px;
  }
  #climb-container .container {
    flex-direction: column;

    margin-left: 0px;
  }
  .schedule-tabs > div {
    min-height: 500px !important;
  }
  footer > div {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 16px;
  }
  p {
    padding: 0 16px;
  }
  .mountain-container {
    display: none;
  }
  .mobile-mountain-container {
    display: flex;
    justify-content: center;
    padding: 24px 16px;
  }
  .vsa-list {
    --vsa-highlight-color: #364659 !important;
  }
  .vsa-item__content .background {
    position: relative;
  }
}
</style>
