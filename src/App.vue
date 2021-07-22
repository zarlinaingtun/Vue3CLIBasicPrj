<template>
  <h1 ref="greet">Vue3 Js</h1>
  <input type="text" ref="name"/>
  <button @click="clickHandler">Click</button>
<br/>
  <!--3.Use -->
  <div v-if="success.showModal">
  <Modal :header="success.header" :content="success.content" :theme="success.theme" @close="success.showModal=false"></Modal>
  </div>
    <div v-if="danger.showModal">
  <Modal :header="danger.header" :content="danger.content" :theme="danger.theme" @close="danger.showModal=false"></Modal>
  </div>
  <button @click.right="success.showModal=true">Show Modal</button>
  <button @click.alt="danger.showModal=true" id="delete">Delete Modal</button>
</template>

<script>
// 1.import
import Modal from "./components/Modal.vue"

export default {
    data(){
      return {
            success:{
                header:"Login Success",
                content:"Welcome From Our App",
                theme:"success",
                showModal:false
            },
            danger:{
                header:"Delete Process",
                content:"Are you sure to delete it ?",
                theme:"delete",
                showModal:false
            }
      }
    },
    methods:{
      clickHandler(){
          // const input=document.getElementsByTagName('input');
          // console.log(input);

          console.log(this.$refs.name);
          this.$refs.name.focus();
          this.$refs.greet.textContent="Greeting";
      },
  
      successClick(){
           const success=document.getElementById('success');
           const danger=document.getElementById('danger');
           console.log(success);
          
           danger.classList.remove('show');
           success.classList.add('show');
      },
      deleteClick(){
           const success=document.getElementById('success');
           const danger=document.getElementById('danger');
           console.log(danger);
           success.classList.remove('show');
           danger.classList.add('show');
      },
     
    },
    components:{
      //2.Register
      // Modal:Modal
      Modal
    }
}
</script>

<style scoped>
#app{
  width: 100vh;
  height: 100vh;
}
h1{
  color:blue;
}

button{
  width:80px;
  height:50px;
  color:#fff;
  font-size: 16px;
 
  border:0;
  margin:5px;
  border-radius: 4px;
}
button:focus{
  transform: scale(0.899);
}
button{
  background-color: green;
}
button#delete{
  background-color: crimson;
}
</style>
