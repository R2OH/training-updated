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
import { exampleMixin } from '../mixins'
export default {
  name: 'devs', 
  props: ['workers'],
	data: function () {
    return {
    
    }
  },
  mixins: [exampleMixin],
  created: function () {
    console.log('devs are created')
    this.$parent.$data.localState.sales = false;
    this.$parent.$data.localState.consultants = false;
    this.$parent.$data.localState.support = false;
  },
  destroyed: function () {
    console.log('devs are destoryed')
  }
}
</script>


<style scoped>
.name{
  display: inline-block;
  width: 100%;
  text-align: center;
}
.job{
  display: inline-block;
  width: 100%;
  text-align: center;
}
.person{
  display: flex;
  margin: 5% 5% 0% 7%;
}
@media screen and (max-width: 1000px) and (min-width: 900px){
  .name{
    color: red;
  }
}

@media screen and (max-width: 1000px) and (min-width: 900px){
  .name{
    color: red;
  }
}
</style>
