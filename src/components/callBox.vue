<template>
  <div class="main">
    hello callbox
    <div class="buttonRow">
        <div v-if='!localState.devs' class="button" @click='showDevs'>
          Show Devs
        </div>
        <div v-if='localState.devs' class="button" @click='hideDevs'>
          hide Devs
        </div>
       <div v-if='!localState.sales' class="button" @click='showSales'>
          Show Sales
        </div>
        <div v-if='localState.sales' class="button" @click='hideSales'>
          hide Sales
        </div>
        <div v-if='!localState.consultants' class="button" @click='showConsultants'>
          Show Consultants
        </div>
        <div v-if='localState.consultants' class="button" @click='hideConsultants'>
          hide Consultants
        </div>
        <div v-if='!localState.support' class="button" @click='showSupport'>
          Show Support
        </div>
        <div v-if='localState.support' class="button" @click='hideSupport'>
          hide Support
        </div>
        
    </div>
    <div class="peopleContainer">
          <devs v-if='localState.devs' v-bind:workers='this.people.hackerFarmers'/>
          <sales v-if='localState.sales' v-bind:workers='this.people.sales'/>
          <consultants v-if='localState.consultants' v-bind:workers='this.people.consultants'/>
          <support v-if='localState.support' v-bind:workers='this.people.support'/>
   </div>
  </div>
</template>

<script>
import devs from './dev.vue'
import sales from './sales.vue'
import consultants from './consultants.vue'
import support from './support.vue'
export default {
  name: 'callBox', 
  components: {
    devs,
    sales,
    consultants,
    support
  },
  data: function (){
    return{
      localState:{
        devs: false, 
        consultants: false,
        sales: false,
        support: false
      },
      people:{
        support: [
         {
          name: 'Scott Castillo',
          job: 'Support'
        },
        {
          name: 'Brittanee Tasby',
          job: 'Support'
        },
        {
          name: 'David Mills',
          job: 'Support'
        },
        {
          name: 'Ben McMurry',
          job: 'Support'
        }
      ],
        sales: [
         {
          name: 'Vonnor Van Hemert',
          job: 'Sales'
        },
        {
          name: 'Brett Spelker',
          job: 'Sales'
        },
        {
          name: 'Steele Haspel',
          job: 'Sales'
        },
        {
          name: 'Seth Elliott',
          job: 'Sales'
        }
      ],
        consultants: [
         {
          name: 'Berryman',
          job: 'Consultant'
        },
        {
          name: 'Dan',
          job: 'Consultant'
        },
        {
          name: 'Erin',
          job: 'Consultant'
        },
        {
          name: 'Harrison',
          job: 'Consultant'
        }
      ],
        hackerFarmers: [
      {
        name: 'Tim',
        job: 'Front End'
      },
      {
        name: 'Dawn',
        job: 'Back End'
      },
      {
        name: 'Eric',
        job: 'Back End'
      },
      {
        name: 'Arjan',
        job: 'Back End'
      },
      {
        name: 'Andy',
        job: 'Back End'
      },
      {
        name: 'Austin',
        job: 'Back End'
      },
      {
        name: 'Jason',
        job: 'QA'
      },
      {
        name: 'Jayah',
        job: 'Project Manager'
      },
      {
        name: 'Wei',
        job: 'UI Developer'
      }
      ]
      }

    }
  },
  methods: {
    showDevs: function () {
      this.localState.devs = true;
    },
    hideDevs: function () {
      this.localState.devs = false;
    },
    showSupport: function () {
      this.localState.support = true;
    },
    hideSupport: function () {
      this.localState.support = false;
    },
    showConsultants: function () {
      this.localState.consultants = true;
    },
    hideConsultants: function () {
      this.localState.consultants = false;
    },
    showSales: function () {
     this.localState.sales= true;
    },
    hideSales: function () {
     this.localState.sales= false;
    }
  }
}
</script>
<style scoped>
.buttonRow{
  display: block;
  background-color: #0cbe7d;
  padding-top: 20px;
  padding-bottom: 20px;
  margin-top: 5%;
  margin-bottom: 5%;
}
.button{
  display: inline-block;
  padding: 10px;
  color: #383838;
  background-color: white;
  border-color: white;
  border-width: 2px;
  cursor: pointer;
  margin-left: 5%;
  margin-right: 5%;
  border-radius: 5px;
  transition: .2s ease;
}
.button:hover{
  background-color: #2d9ef7;
  color: white;
}
.button:active{
  border-color: grey;
}
.peopleContainer{
  overflow-y: scroll;
  overflow-x: hidden;
  height: 400px;
}
</style>
