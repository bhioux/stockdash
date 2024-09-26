<template>
        <tr>
            <td>{{ symbol }}</td>
            <td>{{ open }}</td>
            <td>{{ high }}</td>
            <td>{{ low }}</td>
            <td>{{ close }}</td>
            <td>{{ adjclose }}</td>
            <td>{{ volume }}</td>
        </tr>
 
</template>

<script>
export default {
    props:[
        'stocklist', 'symbol', 'open', 'high', 'low', 'close', 'adjclose', 'volume'
    ],
    components: {
        //
    },
    data(){
        return{
            'stocklist':[],
            category:"Apple"

        }
    },

}
</script>

<style scoped>
    
    td {
        width:11.1%;
        text-align: left;
        border:1px solid blue;
    }
</style>