<template>
  <div id="app">
    <Header />
    <AddLineitem v-on:add-lineitem="addLineitem"/>
    <Lineitems v-bind:lineitems="lineitems" v-on:del-lineitem="deleteLineitem" />
  </div>
</template>

<script>
import Header from "./components/layout/header";
import Lineitems from './components/Lineitems';
import AddLineitem from './components/AddLineitem';

export default {
  name: 'App',
  components: {
    Header,
    Lineitems,
    AddLineitem,
  },
  data() {
    return{
      lineitems:[
      {
        id:1,
        title: "Lineitem One",
        value: 1
      },
      {
        id:2,
        title: "Lineitem Two",
        value: 100
      },
      {
        id:3,
        title: "Lineitem Three",
        value: -1
      }
      ]
    }
  },
  methods: {
    deleteLineitem(id){
      this.lineitems = this.lineitems.filter(lineitem => lineitem.id !== id);
    },
    addLineitem(newLineitem) {
      this.lineitems = [...this.lineitems, newLineitem];
    }
  }
}
</script>

<style>
* {

}

body {
  font-family:  Arial, Helvetica, sans-serif;
  line-height:  1.4;
}
</style>
