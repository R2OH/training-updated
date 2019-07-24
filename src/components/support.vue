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
    },
    destroyed: function () {
        console.log('supporters are destroyed')
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