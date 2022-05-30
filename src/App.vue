<script setup>

// const First_tryy=  'bring all the product to the ware house'
// methods: {
//   handleClick() {
//     console.log(this.$refs)
//   }
// }


</script>

<template>
 

  <main>
    <h1>{{ title }}</h1>
    <p>Bring Market</p>
    <teleport to=".modals" v-if="showModal">
      <Modal theme="sale" @close="toggleModal"> 
        <template v-slot:links>
          <a href="#">sign up</a>
          <a href="#">more info</a>
        </template>
        <h1>Get Your First Next.js Here</h1>
        <p>Acceptance Has Always Been Use Well</p>
      </Modal>

    </teleport>
    <teleport to=".modals" v-if="showUs">
      <Modal @close="toggleMode">
        <h1>Asses Customer Service</h1>
        <p>Select All Product and Add to Card</p>
      </Modal>
    </teleport>
    <button @click="toggleMode">check out</button>
    <button @click.left="toggleModal">open model</button>

    <!-- <input type="text" ref="name">
    <button @click="handleClick">click me</button> -->
  </main>
</template>
<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return{
      title: 'My First Next.js App',
      header:'Sign up for the Giveaway!',
      text:'Grad it and keep it save!',
      showModal:false,
      showUs:false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleMode(){
      this.showUs = !this.showUs
    }
  }
}
</script>

<style>
@import './assets/base.css';

#app.modals {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
