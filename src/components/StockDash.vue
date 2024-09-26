<template>
    <h1>{{ welcome }}</h1>
</template>

<script>
export default {
    props: [
        'welcome',
    ]
}
</script>

<style scoped>
 h1 {
    margin-top:1px;
    border-bottom:1px solid blue;
    border-radius: 4px;;
    box-shadow: 4px 4px lightblue;

 }
</style>