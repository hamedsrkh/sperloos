<template>
  <div class="separator">
    <div class="separator-text">
      <span class="text-disable bg-white pa-1">Date Period</span>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.separator{
  width: calc(100% + 32px);
  background-image: linear-gradient(to right, #A6ACBA 70%, rgba(255,255,255,0) 0%);
  background-position: bottom;
  background-size: 12px 1px;
  background-repeat: repeat-x;
  margin: 24px 0;
  height: 9px;
}
.separator-text{
  color: #A6ACBA;
  text-align: center;
  font-size: 12px;
}
.bg-white{
  background-color: white;
}
.pa-1{
  padding: 10px;
}

</style>
