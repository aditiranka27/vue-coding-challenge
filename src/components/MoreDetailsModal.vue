<template>
  <p class="more-details">
    <button type="button" class="btn" @click="showDialog">
        <img src="../assets/Plus.svg" alt="plus-sign" class="plus-sign">
    </button>
    <span class="details">More Details</span> 
  </p>
  <!-- Dialog-box -->
  <transition enter-active-class="animate__animated animate__bounceIn animate__slow"
    leave-active-class="animate__animated animate__fadeOut" appear>
    <div class="vue-modal modal" role="dialog" v-if="showModal">
      <div>
        <h1 class="modal-heading">Explore</h1>
        <hr class="path">
        <button type="button" class="btn cancel-icon" @click="hideDialog"><i class="bi bi-x "></i></button>
        <p class="read-more">
          Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, 
          totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt 
          explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur 
          magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor 
          sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam 
          aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit 
          laboriosam, nisi ut aliquid ex ea commodi consequatur?
        </p>
        <button type="button" class="btn read-btn">Read More</button>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'MoreDetailsModal',
  data() {
    return {
      showModal: false
    }
  },

  methods: {
    showDialog () {
      this.showModal = true
      this.$emit('clicked', this.showModal)
    },
    hideDialog () {
      this.showModal = false
      this.$emit('clicked', this.showModal)
    }
  }
}
</script>

<style scoped>

.more-details {
  font-family: Arial, Helvetica, sans-serif;
}

.vue-modal {
  display: initial;
  position: fixed;
  top: 15%;
  left: 10%;
  height: fit-content;
  max-width: 27em;
  padding: 2rem;
  margin-right: 5px;;
  box-shadow: 0 5px 5px rgba(0, 0, 0, 0.2);
  background: #FFF;
}

.vue-modal h1 {
  margin: 0 0 1rem;
}

.modal-heading {
  color: #611818;
}

.path {
  background: rgb(97,24,24);
  background: linear-gradient(63deg, rgba(97,24,24,1) 0%, rgb(252, 226, 217) 100%);
  width: 50%;
  height: 1px;
  margin-left:0;
  margin-right: auto;
  border: 0 none;
  opacity: 1;
}

.cancel-icon {
  color: #611818;
  font-size: 2rem;
  position: absolute;
  top:0;
  right:1%;
}

.read-more {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
  color: #000;
  opacity: 0.5;
}

.read-btn {
  background: rgb(97,24,24);
  background: linear-gradient(63deg, rgba(97,24,24,1) 0%, rgba(163,103,84,1) 100%);
  color: #FFF;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
  border-radius: 0%;
  width: 40%;
}
</style>