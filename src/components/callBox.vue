<template>
  <div class="main">
    <img class="logo" src="..\assets\cbLogo\cbwidegray.png">
    <div class="buttonRow">
        <div v-if='!localState.devs' class="button" @click='showDevs'>
          <p class="buttonText">Show Devs</p>
        </div>
        <div v-if='localState.devs' class="button" @click='hideDevs'>
          <p class="buttonText">Hide Devs</p>
        </div>
       <div v-if='!localState.sales' class="button" @click='showSales'>
          <p class="buttonText">Show Sales</p>
        </div>
        <div v-if='localState.sales' class="button" @click='hideSales'>
          <p class="buttonText">Hide Sales</p>
        </div>
        <div v-if='!localState.consultants' class="button" @click='showConsultants'>
          <p class="buttonText">Show Consultants</p>
        </div>
        <div v-if='localState.consultants' class="button" @click='hideConsultants'>
          <p class="buttonText">Hide Consultants</p>
        </div>
        <div v-if='!localState.support' class="button" @click='showSupport'>
          <p class="buttonText">Show Support</p>
        </div>
        <div v-if='localState.support' class="button" @click='hideSupport'>
          <p class="buttonText">Hide Support</p>
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
  /* padding-top: 20px;
  padding-bottom: 20px;
  margin-top: 5%;
  margin-bottom: 5%; */
}
.button{
  display: inline-block;
  padding: 10px;
  color: #383838;
  background-color: white;
  border-color: white;
  border-width: 2px;
  cursor: pointer;
  /* margin-left: 5%;
  margin-right: 5%; */
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
.logo {
  margin: 5% 0;
  max-width: 50%
}
.main {
  max-width: 100%;
}
/* mobile */
@media screen and (max-width: 455px){
  .buttonRow{
    max-width: 100%;
    margin:0%;
    padding:0%;
    border: 5px solid #0cbe7d;
  }
  .button{
    display: flex;
    border: 5px solid white;
    border-collapse: collapse;
    margin:5%;
    padding:4%;
    position: relative;
  }
  .buttonText {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    margin:0%;
  }
}
/* tablet */
@media screen and (min-width: 455px){
  .buttonRow{
    background-color: blue;
    display: flex;
  }
}
</style>
