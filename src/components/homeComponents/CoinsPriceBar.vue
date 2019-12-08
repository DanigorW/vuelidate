<template>
  <div class="coins-price">
      <ul >
          
          <li 
        
           v-for="(item, index) in coins" :key="index">
              {{item[0]}}/BTC <span v-for="(price, index) in item" :key="index">
                  {{price.last}} </span>
                  
          </li>
              
     </ul>
  </div>
</template>

<script>

export default {

    
    name: "CoinsPriceBar",
    data(){
        return{
           coins: [],
           coinsMd: [],
           coinsSm: [],
           coinsXs: []
        }
    },

    methods: {
        getData(data){
        let fromObjToArray = Object.entries(data)
        this.coins = fromObjToArray;    
        this.coins.splice(10)
        
        },
    },

    created(){
        fetch("https://blockchain.info/ticker")
        .then(req => req.json())
        .then(req => this.getData(req))
        .catch(err => alert(err))
    },

    computed: {
       
    }

}
</script>

<style lang="scss">
    .coins-price {
        background: #000;
        padding: 12px 20px;
        color: #fff;

        ul {
        list-style: none;    
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        }

        li {
            font-size: 13px
        }
    }


    @media (max-width: 1363px) {
        ul {
            justify-content: center;
        }
    }
    
</style>