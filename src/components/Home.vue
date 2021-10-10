<template>
  <section>
    <div class="container-fluid">
      <div class="row">
        <!-- side-bar -->
        <div class="col-sm-4" id="side-bar">
        </div>
        
        <!-- Explore -->
        <div class="col-sm-3 col-sm-offset-4  overlay-text">
          <transition enter-active-class="animate__animated animate__fadeInLeft" appear>
            <h1 class="heading" v-if="showExplore">Explore</h1>
          </transition>
          
          <!-- More-details -->
          <more-details-modal v-on:clicked="modalClicked"></more-details-modal>
        </div>

        <!-- fb-icon -->
        <div class="col-sm-3 col-sm-offset-4 fb-icon">
          <img src="../assets/facebook.svg" alt="fb-icon">
        </div>

        <!-- instagram-icon -->
        <div class="col-sm-3 col-sm-offset-4 instagram-icon">
          <img src="../assets/Instagram.svg" alt="instagram-icon">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import MoreDetailsModal from './MoreDetailsModal.vue'
export default {
  components: { MoreDetailsModal },
  name: 'Home',
  data() {
    return {
      showExplore: true
    }
  },

  methods: {
    modalClicked (value) {
      this.showExplore = !value
    }
  }
}
</script>

<style scoped>

/* Side-bar */
#side-bar{
  background-color: #611818;
  height: 100vh;
  width: 413px;
}

/* Heading */
.overlay-text {
  position:absolute;
  bottom: 30%;
  left: 15%;
  font-family: 'Playfair Display', serif;
}

.heading{
  font-size: 10rem;
}

/* icons */
.instagram-icon{
  position: absolute;
  bottom:5%;
  left: 90%;
}

.fb-icon{
  position: absolute;
  bottom: 18%;
  left: 90%;
}

/* Responsive-css */
@media screen and (max-width:414px){
  body{
    font-size: 14px;
  }
  #side-bar{
  max-width: 25%;
  }
  .overlay-text{
    position:absolute;
    left:5%;
  }
  .heading{
    font-size: 5rem;
  }
  .plus-sign{
    width:30px;
    height:30px;
  }
  .details{
    display: none;
  }
  .fb-icon,.instagram-icon{
    position: absolute;
    left:75%;
  }  
}

@media screen and (max-width:823px){
  body{
    font-size: 14px;
  }
  #side-bar{
  max-width: 25%;
  }
  .overlay-text{
    position:absolute;
    left:12%;
    bottom: 50%;
  }
  .heading{
    font-size: 5rem;
  }
  .plus-sign{
    width:30px;
    height:30px;
  }

  .fb-icon{
    position: absolute;
    left:75%;
    bottom:20%;
  }
  .instagram-icon{
    position: absolute;
    left:75%;
    bottom:10%;
  }
}
</style>
