<template>
  <vsa-list>
    <vsa-item>
      <vsa-heading> Mountain 1 </vsa-heading>

      <vsa-content>
        <div style="position: relative">
          <img
            class="schedule"
            src="..\..\src\assets\tab-1-schedule.png"
            alt="Schedule"
          />
        </div>
        <div>
          <img
            class="background"
            src="..\..\src\assets\mountain-image.png"
            alt="Background"
          />
        </div>
      </vsa-content>
    </vsa-item>
    <vsa-item>
      <vsa-heading> Mountain 2 </vsa-heading>

      <vsa-content>
        <div style="position: relative">
          <img
            class="schedule"
            src="..\..\src\assets\tab-2-schedule.png"
            alt="Schedule"
          />
        </div>
        <div>
          <img
            class="background"
            src="..\..\src\assets\mountain-image1.png"
            alt="Background"
          />
        </div>
      </vsa-content>
    </vsa-item>
  </vsa-list>
</template>
<script>
import { VsaList, VsaItem, VsaHeading, VsaContent, VsaIcon } from "vue-simple-accordion";
import "vue-simple-accordion/dist/vue-simple-accordion.css";

export default {
  components: { VsaList, VsaItem, VsaHeading, VsaContent, VsaIcon },
};
</script>
