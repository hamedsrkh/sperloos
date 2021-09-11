<template>
  <div class="card">
    <div class="card-info" v-if="isActive">
      <span class="badge badge-purple">CREAT BOOST</span>
      <Separator/>
      <p class="picker-title">Pick Date Range:</p>
      <div class="date-picker">
        <div class="date">2020/09/10</div>
        <span class="text-disable">To</span>
        <div class="date">2020/09/10</div>
      </div>
    </div>
    <div class="card-summery" v-else>
      <div class="badge">BOOST</div>
      <div class="card-footer">
        <span class="title">LIKING</span>
        <span class="counter">{{ item.likes }}</span>
      </div>
    </div>
    <div class="expand" :class="{ active: isActive }" @click="activateCard">
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><defs>
      </defs>
        <g transform="translate(-149 -18)"><rect fill="none" width="24" height="24" transform="translate(149 18)"/>
          <path class="b" d="M25.91,16.875H19.125V10.09a1.125,1.125,0,0,0-2.25,0v6.785H10.09a1.125,1.125,0,0,0,0,2.25h6.785V25.91a1.125,1.125,0,0,0,2.25,0V19.125H25.91a1.125,1.125,0,0,0,0-2.25Z" transform="translate(143.035 12.035)"/>
        </g>
      </svg>
    </div>
  </div>
</template>

<script>
import Separator from "./Separator";
export default {
  components: {Separator},
  props:{
    active: {
      type: Number,
      default: 0
    },
    item:{
      required: true
    }
  },
  data(){
    return{

    }
  },
  computed: {
    isActive(){
      return this.active === this.item.id
    }
  },
  methods:{
    activateCard(){
      this.$emit('change-active-card',{id:this.props.item.id})
    }
  }
}
</script>

<style scoped>
 .card{
   width: 256px;
   background: #FFFFFF 0 0 no-repeat padding-box;
   border: 1px solid #EAEAEA;
   border-radius: 8px;
   opacity: 1;
   margin-right: 16px;
   margin-bottom: 50px;
   padding: 24px 16px;
   position: relative;
   color: #3C3C3C;
 }
 .badge{
   border: 1px solid #CCD0DE;
   border-radius: 13px;
   font: normal normal normal 11px/12px Arial;
   color: #CCD0DE;
   padding: 6px 12px;
   display: inline-flex;
   align-items: center;
 }
 .badge.badge-purple{
   background: #4F5BD51F 0 0 no-repeat padding-box;
   text-align: left;
   font: normal normal normal 12px/14px Arial;
   color: #4F5BD5;
 }
 .card-footer{
   display: flex;
   align-items: center;
   justify-content: space-between;
   margin-top: 25px;
 }
 .card-footer .title{
   line-height: 18px;
   font-size: 16px;
 }
 .card-footer .counter{
   line-height: 34px;
   font-weight: bold;
   font-size: 30px;
 }
 .expand{
   display: flex;
   align-items: center;
   justify-content: center;
   position: absolute;
   top: -10px;
   left: 50%;
   transform: translateX(-50%);
   width: 232px;
   height: 40px;
   padding: 10px;
   background: #FFFFFF 0 0 no-repeat padding-box;
   border: 1px solid #EAEAEA;
   border-radius: 8px 8px 0 0;
   z-index: -1;
   transition: transform 0.3s ease-out;
 }
 .expand .b{
   fill:#4f5bd5;
 }
 .expand.active .b{
   fill:#fff;
 }
 .expand.active{
   background: #4F5BD5 0 0 no-repeat padding-box;
   transform: translate(-50%, -30px);
 }
 .card:hover .expand:not(.active){
   transform: translate(-50%,-30px);
   z-index: 0;
 }
 .card-info{
   display: flex;
   flex-direction: column;
   justify-content: flex-start;
   align-items: center;
   min-height: 340px;
 }
 .picker-title{
   line-height: 14px;
   font-size: 12px;
 }
 .date-picker{
   display: flex;
   justify-content: space-around;
   align-items: center;
   width: 100%;
 }
 .date-picker .date{
   line-height: 16px;
   font-size: 14px;
   color: #3C3C3C;
   padding: 5px 0;
   border-bottom: 1px solid #707070;
 }
</style>
