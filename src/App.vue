<script>

import TheHeader from "./components/TheHeader.vue";
import TheFooter from "./components/TheFooter.vue";
import TheBlueBar from "./components/TheBlueBar.vue";
import CardContainer from "./components/CardContainer.vue";

export default {
  components: {
    TheHeader,
    TheFooter,
    TheBlueBar,
    CardContainer
  }
}

</script>

<template>
  <TheHeader></TheHeader>

  <main>
    <div class="jumbotron"></div>

    <div class="content-container">
      <span class="btn-big">current series</span>
      <CardContainer></CardContainer>

      <div class="row-btn">
        <span class="btn">load more</span>
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
  padding: 65px 0 20px;
  position: relative;
}

.jumbotron {
  height: 290px;
  background-image: url("./assets/jumbotron.jpg");
  background-size: cover;
}

.row-btn {
  text-align: center;
}
.btn {
  @include pill;
  @include text-white;
  background-color: $color_primary;
  padding: 10px 30px;
  font-weight: 600;
  margin-top: 50px;
  font-size: 14px;
  cursor: pointer;
}
.btn-big {
  @include pill;
  @include text-white;
  background-color: $color_primary;
  font-weight: 600;
  padding: 10px 20px;
  font-size: 18px;
  position: absolute;
  left: 175px;
  top: -20.5px;
  cursor: pointer;
}
</style>