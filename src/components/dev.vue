<template>
  <div class="main">
      <div :key="hackerFarmer.name" class="person" v-for='hackerFarmer in workers'>
        <div :key="hackerFarmer.name" class="name"> 
          {{hackerFarmer.name}}
        </div>
        <div :key="hackerFarmer.job" class="job">
          {{hackerFarmer.job}}
        </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'devs', 
  props: ['workers'],
	data: function () {
    return {
    
    }
  },
  created: function () {
    console.log('devs are created')
  },
  destroyed: function () {
    console.log('devs are destoryed')
  }
}
</script>


<style scoped>
.name{
  display: inline-block;
  width: 200px;
  text-align: left;
}
.job{
  display: inline-block;
  width: 200px;
  text-align: right;
}
.person{
  display: block;
  margin-bottom: 50px;
}

</style>
