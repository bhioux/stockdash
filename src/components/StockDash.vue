<template>
    <div>
        <h1 v-bind:title="appname">{{ welcome }}</h1>
        <h3>This is the {{ appname }} app</h3>
    </div>
    
</template>

<script>
export default {
    props: [
        'welcome',
    ],
    inject: ['appname']
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