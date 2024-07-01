<template>
  <h1>{{title}}</h1>
<p>welcome....</p>
  <div v-if="showModal" >
    <Modal :header="header" :text="text" theme="sale" @close="show"/>
  </div>
  <button @click.ctrl="show">Showmodal (ctrl)</button>

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
      showModal: false
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
    close(){
      console.log('hi')
    
  }
}
    
}
</script>

<style>
#app {
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
