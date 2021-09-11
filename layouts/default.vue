<template>
  <div class="container pt-5">
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: "default"
}
</script>

<style>
 *, *::after, *::before{
   box-sizing: border-box;
 }
body{
  height: 1080px;
  background: #F8F8F8 0 0 no-repeat padding-box;
  opacity: 1;
  font-family: Arial,serif;
}
.container{
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}
.pt-5{
  padding-top: 5rem;
}
@media (min-width: 1200px) {
  .container, .container-sm, .container-md, .container-lg, .container-xl {
    max-width: 1140px;
  }
}
 .text-disable{
   color: #A6ACBA;
 }
</style>
