<template>
  <div class="main">
        <div v-bind:key="person.name" class="person" v-for='person in workers'>
        <div :key="person.name" class="name"> 
          {{person.name}}
        </div>
        <div :key='person.job' class="job">
          {{person.job}}
        </div>
        </div>
  </div>
</template>

<script>

export default {
  name: 'sales', 
  props: ['workers'],
	data: function () {
    return {
     
    }
  },
  created: function () {
    console.log('sales are created')
    this.$parent.$data.localState.devs = false;
    this.$parent.$data.localState.consultants = false;
    this.$parent.$data.localState.support = false;
  },
  destroyed: function () {
    console.log('sales are destoryed')
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
  margin: 5% 5% 20% 7%;
}

</style>
