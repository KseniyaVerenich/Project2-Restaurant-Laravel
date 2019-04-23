<template>
  <div>
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-10">
          <div class="row justify-content-center" style="margin: 20px;">
            <div class="col-5" v-for="n in 4" :key="n">
              <!-- Card Flip -->
              <cards :n="n"></cards>

              <!-- End Card Flip -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import cards from "./cards";
export default {
  components: {
    cards
  }
};
</script>


<style>

.container {
  font-family: 'Quicksand', sans-serif;

}

</style>