<template>
  <div class="main">
    <div :key="consultant.name" class="person" v-for='consultant in workers'>
      <div :key="consultant.name" class="name">
        {{consultant.name}}
      </div>
        <div :key="consultant.job" class="job">
          {{consultant.job}}
        </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'consultants', 
  props: ['workers'],
	data: function () {
    return {
    
    }
  },
  created: function () {
    console.log('consultants are created')
    this.$parent.$data.localState.sales = false;
    this.$parent.$data.localState.devs = false;
    this.$parent.$data.localState.support = false;
  },
  destroyed: function () {
    console.log('consultants are destoryed')
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
