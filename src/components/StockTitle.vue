<template>
  <h2>Viewing <span class="title">{{ title }}</span> stock list</h2>
</template>

<script>
export default {
    data(){
        return{
            'title': "Apple"
        }
    }
}
</script>

<style>
    h2 {
        padding:3px 0px;
    }

    h2 .title{
        color:red;
        font-weight: 600;
    }
</style>