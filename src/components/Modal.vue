<template>
  <div class="backdrop">
      <div class="modal">
          <p>Modal content</p>
      </div>
  </div>
 
</template>

<script>
export default {

}
</script>

<style>
  .backdrop{
      background-color: rgba(0,0,0,0.5);
      width:100%;
      height:100%;

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
      border-radius: 10px;
      background-color: #fff;
  }
</style>