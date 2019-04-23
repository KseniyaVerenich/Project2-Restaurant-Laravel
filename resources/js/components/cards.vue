<template>
  <div>
    <div class="card-flip">
      <div class="flip">
        <div class="front">
          <!-- front content -->
          <div class="card">
            <img v-bind:src="'/img/' + n + '.jpg'" class="card-img-top" alt="100%x180">
          </div>
        </div>

        <div class="back">
          <!-- back content -->
          <div class="card">
            <div class="card-block"></div>

            <div class="card-block">
              <p class="card-text"  v-for="item in menu_array" :key="item.description">{{item.description}}</p>
           
           
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
       
        
      myJson: null,
      menu_array: []
    };
  },
   props: {
    n: Number
  },
  methods: {
 
    //save the array (not description) 
        //in template do a v-for for all items in the array
   
    processData() {

 
      this.menu_array = this.myJson.menu_items
      //);
      console.log("53",this.menu_array);
      //this.menu_array = this.menu_array.slice(1, -1);
    },
    //    display() {
    // console.log("display");
    // this.getApi();
    // this.processData();
    
    // },
  },
 

    mounted() {

    

        console.log("getApi")
      var self = this;
      axios

        .get(
          "https://cors-anywhere.herokuapp.com/" +
            "https://entree-f18.herokuapp.com/v1/menu/8"
        )
        .then(response => {
          self.myJson = response.data;
          self.processData()
        
        });
    },

  
  


//   computed: {
//      onPage() {
//          this.display;
//          return this. description;
//      }
 
//   }
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

#text {
  font-family: 'Quicksand', sans-serif;
  

}

</style>