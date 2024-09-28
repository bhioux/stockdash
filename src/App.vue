<template>
  <div>
    <StockDash welcome='You are welcome to stock dashboard' />
    <StockTitle />
    <StockSearch @dosearch="searchStock" />
    <Input v-model="name" />
    <table>
      <StockList v-for="stock in filteredStock" :key="stock.id"  :symbol="stock.symbol" :open="stock.open" :high="stock.high" :low="stock.low" :close="stock.close" :adjclose="stock.adjclose" :volume="stock.volume"  />
    </table>
    <hr />
    <!-- <Card>
      <template v-slot:header="slotProps">
          <h2>{{ slotProps.cardtype }}</h2>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/300" />
      </template>
      <template v-slot:footer>
        <h4>Lovely image courtesy: Picsum photos</h4>
      </template>      
    </Card> -->
    <hr />
    <PostList />
  </div>
  
</template>

<script>

import StockDash from "./components/StockDash.vue";
import StockTitle from "./components/StockTitle.vue";
import StockList from "./components/StockList.vue";
import StockSearch from "./components/StockSearch.vue";
import Input from "./components/Input.vue";
// import Card from "./components/Card.vue";
import PostList from "./components/PostList.vue";


export default {
  components: {
    StockDash,
    StockTitle,
    StockSearch,
    StockList,    
    Input,
    // Card,
    PostList,
  },
  data(){
    return{
      'stocklist':
            [
                {
                    "id": 1,
                    "date": "2024-05-03",
                    "open": "0.26488",
                    "high": "0.28199",
                    "low": "0.26425",
                    "close": "0.27649",
                    "adjclose": "0.27649",
                    "volume": 13530,
                    "symbol": "BTC-USD"
                },
                {
                    "id": 2,
                    "date": "2024-05-04",
                    "open": "0.27649",
                    "high": "0.27649",
                    "low": "0.27633",
                    "close": "0.27634",
                    "adjclose": "0.27634",
                    "volume": 27538,
                    "symbol": "BTC-USD"
                },
                {
                    "id": 3,
                    "date": "2024-05-05",
                    "open": "0.27634",
                    "high": "0.27642",
                    "low": "0.27582",
                    "close": "0.27599",
                    "adjclose": "0.27599",
                    "volume": 30598,
                    "symbol": "BTC-USD"
                },
                {
                    "id": 4,
                    "date": "2024-05-06",
                    "open": "0.27599",
                    "high": "0.27620",
                    "low": "0.27520",
                    "close": "0.27613",
                    "adjclose": "0.27613",
                    "volume": 0,
                    "symbol": "BTC-USD"
                },
                {
                    "id": 5,
                    "date": "2024-05-07",
                    "open": "0.27613",
                    "high": "0.27613",
                    "low": "0.27092",
                    "close": "0.27092",
                    "adjclose": "0.27092",
                    "volume": 0,
                    "symbol": "BTC-USD"
                },
                {
                    "id": 6,
                    "date": "2024-05-08",
                    "open": "0.27092",
                    "high": "0.29052",
                    "low": "0.25018",
                    "close": "0.25653",
                    "adjclose": "0.25653",
                    "volume": 5086461,
                    "symbol": "BTC-USD"
                },
            ],
      'filteredStock': [],
      'result':[],
      s:'',
      name: ''
        
    }
  },
  methods: {
    
    compare(q){
      const a = q.symbol.toUpperCase().includes(this.s.toUpperCase());
      console.log(a)
      return a;
    }, 

    searchStock(s){         
      this.s = s
      return  this.filteredStock = this.stocklist.filter(this.compare);
      console.log(result)
    },

  },
  computed: {
    //
  },
  watch: {
    s: {
      handler(newval, oldval){ 
        if(newval === '' && (oldval === '' || oldval === undefined) ){
          this.filteredStock = this.stocklist
          console.log('New search - Old Value : ' + oldval)
        }else{
          console.log("Active search")
          console.log('Old search - New Value : ' + newval)
          console.log('Old search - Old Value : ' + oldval)
        }
      },
      immediate: true
    }
  },
  provide: {
    appname: 'Stock Dash'
  }
}
</script>

<style scoped>
  
  table { 
        /* min-width: 1024px; */
        width:1024px;
        /* table-layout:fixed; */
        border:1px solid blue;
        border-collapse:collapse;
        box-shadow: 4px 4px red;
    }

    hr{
      margin: 30px 0;
    }


</style>
