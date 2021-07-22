<template>
  <div class="backdrop">
      <div class="modal" :class="{success:theme==='success',danger:theme==='delete'}">
        <h1>Modal Title</h1>
          <p>Modal content</p>
          <span>{{header}}</span>
          <span>{{content}}</span>
      </div>
  </div>
 
</template>

<script>
export default {
      props:['header','content','theme']
}
</script>

<style scoped>

  .backdrop{
      /* background-color: rgba(0,0,0,0.5); */
      width:500px;
      height:500px;
      background-color: transparent;
      margin:200px 50px 0px 50px;

      

      display: flex;
      justify-content: center;
      align-items: center;

      position: absolute;
      top:0;
      left: 0;
  }
  .modal{
      width:400px;
      padding:10px;
      border:5px solid palegreen;
      box-shadow: 0px 10px 10px rgba(0,0,0,0.5);
      
      border-radius: 10px;
      background-color: rgb(21, 189, 167);
  }
  p{
    font-style: normal;
  }
  .success{
    background-color: green;
    color:#fff;
  }
  .danger{
    background-color: crimson;
    color:#fff;
  }

  
</style>