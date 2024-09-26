<template>
  <div>
    <input @change="onSearch" v-model="search" class="search" type="text" v-model.lazy="search" palceholder="search text..." />
  </div>
</template>

<script>
export default {
    data(){
        return{
            search:''
        }
    },
    methods: {
        onSearch(){            
            let s = this.search;
            console.log(s);
            this.$emit('dosearch', s);           
        }
    }

}
</script>

<style scoped>
    .search{
        width:200px;
        height: 20px;
        margin:3px 0 5px 0;
        border: none;
        border-bottom: 2px solid red;
        border-left: 2px solid red;
        outline: none;
        transition: width 0.4s ease-in-out;
        float:right;
    }

</style>