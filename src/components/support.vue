<template>
  <div class="main">
      <div :key="support.name" class="person" v-for='support in workers'>
        <div :key="support.name" class="name">
          {{support.name}}
        </div>
        <div :key="support.job" class="job">
          {{support.job}}
        </div>
      </div>
  </div>
</template>

<script>

export default {
  name: 'support',
  props:['workers'],
  data: function () {
      return {

      }
  },
  created: function () {
    console.log('supporters are created')
    this.$parent.$data.localState.sales = false;
    this.$parent.$data.localState.consultants = false;
    this.$parent.$data.localState.devs = false;
  },
  destroyed: function () {
      console.log('supporters are destroyed')
  }
}
</script>


<style scoped>
.name{
  display: inline-block;
  width: 100%;
  text-align: left;
}
.job{
  display: inline-block;
  width: 100%;
  text-align: right;
}
.person{
  display: flex;
  margin: 5% 5% 20% 7%;
}

</style>