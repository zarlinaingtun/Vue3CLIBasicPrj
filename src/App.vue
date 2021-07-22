<template>
  <h1 ref="greet">Vue3 Js</h1>
  <input type="text" ref="name"/>
  <button @click="clickHandler">Click</button>
  <div class="btn">
    <button @click="successClick">Success</button>
    <button @click="deleteClick">Delete</button>
  </div>


  <!--3.Use -->
  <Modal class="hide" :header="success.header" :content="success.content" :theme="success.theme" id="success"></Modal>
  <Modal class="hide" :header="danger.header" :content="danger.content" :theme="danger.theme" id="danger"></Modal>
  <!-- <Modal/> -->
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
                theme:"success"
            },
            danger:{
                header:"Delete Process",
                content:"Are you sure to delete it ?",
                theme:"delete"
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

.hide{
  display: none;
}
.show{
  display: block;
}
.btn{
  padding:20px;
}
.btn button{
  width:80px;
  height:50px;
  color:#fff;
  font-size: 16px;
 
  border:0;
  margin:5px;
  border-radius: 4px;
}
.btn button:focus{
  transform: scale(0.899);
}
button:nth-child(1){
  background-color: green;
}
button:nth-child(2){
  background-color: crimson;
}
</style>
