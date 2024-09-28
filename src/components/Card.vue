<template>
  <div class="card">
    <slot name="header" :cardtype="cardtype"></slot>
    <slot></slot>
    <slot name="footer"></slot>
  </div>
</template>

<script>
export default {
    name: 'Card',
    data(){
        return {
            cardtype:'My Image Viewer',
        }
    }
}
</script>

<style>
    .card{
        display: block;
        width:400px;
        padding:5px;
        margin:10px auto;
        text-align: center;
        background-color: rgb(247, 248, 248);
        box-shadow: -4px -4px 2px rgb(156, 212, 232);
    }

    .card:hover{
        box-shadow: 4px 4px 2px rgb(76, 193, 235);
    }
</style>