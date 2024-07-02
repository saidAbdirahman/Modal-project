<template>
  <h1>{{title}}</h1>
<p>welcome....</p>
  <teleport to=".modals" v-if="showModal" >
    <Modal  theme="sale" @close="show">
      <template v-slot:links>
        <a href="#">sign up for now</a>
        <a href="#">nore info</a>
      </template>
      <h1>Siciid Giveaway </h1>
      <p> come and get it please</p>
    </Modal>
  </teleport>
 
  <div v-if="show2Modal" >
    <Modal  theme="" @close2="show2">
      <template v-slot:names>
        <p>said</p>
        <p>abdi</p>
      </template>
      <h1>Moha Giveaway </h1>
      <p> come and get it please</p>
    </Modal>
  </div>
  <button @click.ctrl="show">Showmodal (ctrl)</button>

  <button @click="show2">show2Modal</button>


</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',

  components:{
    Modal
  },

  data(){
    return {
      title:'My First Vue App',
      header: 'Sign Up For The Giveaway',
      text: 'come and get it please',
      showModal: false,
      show2Modal: false
    }
  },
  methods:{
    handleEvent(){
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
    },
    show(){

      this.showModal = !this.showModal;

    },
    show2(){

      this.show2Modal=!this.show2Modal

    },
    close(){
      console.log('hi')
    
  }
}
    
}
</script>

<style>
#app,.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
.modal.sale{
  background: crimson;
  color: white;
}
.modal.sale h1{

  color: white;
}
</style>
