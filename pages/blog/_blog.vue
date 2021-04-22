<template>
  <div><h1>hello</h1></div>
</template>
<script>
export default {
   created(){
       console.log(this.$route.params)
   }
}
</script>