<template>
  <div>
      <div class="container">
   
    
        <div class="row">
          <div class="col" v-for="n in 4" :key="n">
            <!-- Card Flip -->
            <div class="card-flip">
              <div class="flip">
                <div class="front">
                  <!-- front content -->
                  <div class="card">
                    <img
                        v-bind:src="'/img/' + n + '.jpg'"
                        class="card-img-top"
                        alt="100%x180"
                        
                 
                       
                    >
                    
                  </div>
                </div>

                <div class="back">
                  <!-- back content -->
                  <div class="card">
                    <div class="card-block">
                      <h4 class="card-title">Card Flip</h4>
                      <h6 class="card-subtitle text-muted">Support card subtitle</h6>
                    </div>
                    <img
                      data-src="holder.js/100px180/?text=Image"
                      alt="Image [100%x180]"
                      data-holder-rendered="true"
                      style="height: 180px; width: 100%; display: block;"
                    >
                    <div class="card-block">
                      <p class="card-text">TEXT</p>
                      <a href="#" class="card-link">Card link</a>
                      <a href="#" class="card-link">Another link</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <!-- End Card Flip -->
          </div>
        </div>
     
    
         
 
    </div>
  </div>
</template>

<script>
export default {
 

  
};
</script>

<style lang="scss" scoped>
.card-flip {
  perspective: 1000px;
  &:hover .flip,
  &.hover .flip {
    transform: rotateY(180deg);
  }
}

.card-flip,
.front,
.back {
  width: 100%;
  height: 480px;
}

.flip {
  transition: 0.6s;
  transform-style: preserve-3d;
  position: relative;
}

.front,
.back {
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
}

.front {
  z-index: 2;
  transform: rotateY(0deg);
}

.back {
  transform: rotateY(180deg);
}
</style>