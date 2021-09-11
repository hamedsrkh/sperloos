<template>
  <div class="card-items">
    <card v-for="item in items" :item="item" :key="item.id" :active="activeCard" @changeActiveCard="changeActiveCard" />
  </div>
</template>

<script>
import Card from "../components/Card";
export default {
  components: {Card},
  data(){
    return{
      activeCard: 1,
      items: [
        {id: 1, likes: 100},
        {id: 2, likes: 100}
      ]
    }
  },
  methods:{
    changeActiveCard({id}){
      this.activeCard = id
    }
  }
}
</script>

<style>
 .card-items{
   display: flex;
   flex-wrap: wrap;
   align-items: flex-start;
 }
</style>
