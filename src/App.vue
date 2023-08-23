<script>

import TheHeader from "./components/TheHeader.vue";
import TheFooter from "./components/TheFooter.vue";
import TheBlueBar from "./components/TheBlueBar.vue";

export default {
  components: {
    TheHeader,
    TheFooter,
    TheBlueBar
  }
}

</script>

<template>
  <TheHeader></TheHeader>

  <main>
    <div class="content-container">
      <div class="content">
        <h2 class="title">
          &rarr; Content goes here &larr;
        </h2>
      </div>
    </div>
    <TheBlueBar></TheBlueBar>
  </main>

  <TheFooter></TheFooter>
</template>


<style lang="scss">
     @use "./styles/partials/variables.scss" as *;
     @use "./styles/partials/mixins.scss" as *;

     .content-container {
      background-color: #1C1C1C;
      padding: 40px 0;
     }
     .content {
      @include space-position;
     }
     .title {
      color: white;
     }

</style>