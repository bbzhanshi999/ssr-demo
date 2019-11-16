<template>
  <ul>
      <li v-for="item in goodList" :key="item._id">
          <h5>{{item.itemName}}</h5>
          <h4>{{item.price}}</h4>
      </li>
  </ul>
</template>

<script>
export default {
    data () {
        return {
            goodList:[]
        }
    },
    async asyncData ({app}){
        const {data} = await app.$axios.get("/goods/list");
        return {goodList:data};
    }
    
}
</script>

<style>

</style>