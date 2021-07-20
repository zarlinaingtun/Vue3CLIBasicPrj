<template>
  <h1 ref="greet">Hi</h1>
  <input type="text" ref="name"/>
  <button @click="clickHandler">Click</button>

  <!--3.Use -->
  <Modal></Modal>
  <Modal/>
</template>

<script>
// 1.import
import Modal from "./components/Modal.vue"

export default {
    data(){
      return {
        title:"You don't know js"
      }
    },
    methods:{
      clickHandler(){
          // const input=document.getElementsByTagName('input');
          // console.log(input);

          console.log(this.$refs.name);
          this.$refs.name.focus();
          this.$refs.greet.textContent="Greeting";
      }
    },
    components:{
      //2.Register

      Modal
      // Modal:Modal
    }
}
</script>

<style>
#app{
  width: 100vh;
  height: 100vh;
}
</style>
