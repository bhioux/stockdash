<template>
  <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
</template>

<script>
export default {
    name: "Input",
    data(){
        return{
            //         
        }
    },
    props: {
        modelValue: String,
    }
        

}
</script>

<style scoped>
    input{
        outline: none;
        width: 200px;
    }
</style>