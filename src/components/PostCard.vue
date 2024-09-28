<template>
    <div class="postcard">
        <slot name="header"></slot>
        <slot></slot>
        <slot name="footer"></slot>
    </div>
</template>
  
  <script>
  export default {
      name: 'PostCard',
      data(){
          return {
            //
          }
      }
  }
  </script>
  
  <style scoped>
      .postcard{
          display: block;
          border: 1px solid blue;
          width:100%;
          padding:10px;
          margin:10px auto;
          text-align: center;
          background-color: rgb(247, 248, 248);
          box-shadow: -4px -4px 2px rgb(156, 212, 232);
      }
  
      .postcard:hover{
          box-shadow: 4px 4px 2px rgb(76, 193, 235);
      }
  </style>