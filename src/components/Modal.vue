<template>
    <div class="backdrop"  @click.self="hide">
        <div class="modal" :class="{sale: theme==='sale'}">
           <slot></slot>
           <div class="action">
            <slot name="links"></slot>
            <slot name="names"></slot>
           </div>
           <div v-if="!showModal">
            <button @click.right="hide">hide modal</button>
           </div>
            
            <button @click="hide2">hide modal2</button>
          
        </div>
    </div>
</template>

<script>

export default {
    props: ['theme'],
    methods:{
        hide(){
           
            this.$emit('close');
        }
        ,
        hide2(){
           
           this.$emit('close2');
       }
    }
    
}
</script>


<style >
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    
}
.modal p{
    font-style: normal;
}
.modal h1{
    color: #03cfb4;
    border: none;
    padding: 0;

}
.modal .action{
    text-align: center;
    margin: 30px 0 10px 0;
    color:#333;

}
.modal.action a{
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;

}
.modal.sale{
    background: crimson;
    color: white;
}
.modal.sale h1{
    color: white;
}

.modal.sale.action{
    color: white;
}
.modal.sale.action a{
    color: white;
}
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}
h1{
    color: #03cfb4;
    border: none;
    padding: 0;
}
</style>