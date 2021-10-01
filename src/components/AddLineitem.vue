<template>
  <div>
    <form @submit="addLineitem">
      <input type="text" v-model="title" name="title" placeholder="Add line-item...">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
  name: "AddLineitem",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addLineitem(e) {
      e.preventDefault();
      const newLineitem = {
        id: uuidv4(),
        title: this.title,
        value: null
      }
      this.$emit('add-lineitem', newLineitem);

      this.title = '';
    }
  }
}
</script>

<style scoped>
	form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
</style>