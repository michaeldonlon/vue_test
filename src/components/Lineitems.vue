<template>
  <div>
    <div v-bind:key="lineitem.id" v-for="lineitem in lineitems">
      <LineitemItem v-bind:lineitem="lineitem" v-on:del-lineitem="$emit('del-lineitem', lineitem.id)"/>
    </div>
  </div>
</template>

<script>
import LineitemItem from './LineitemItem.vue';

export default {
  name: "Lineitems",
  components: {
    LineitemItem
  },
  props: ["lineitems"]
}
</script>

<style scoped>

</style>