<template>
	<div class="lineitem-item" v-bind:class="{'is_negative':lineitem.value < 0}">
		<p>{{lineitem.title}}
		<input type="number" v-on:change="refreshCalc">
		<button @click="$emit('del-lineitem', lineitem.id)" class="del">x</button>
	</p>
	</div>
</template>

<script>
export default {
	name: "LineitemItem",
	props: ["lineitem"],
	methods: {
		refreshCalc(){
			console.log(123)
		}
	}
}
</script>

<style scoped>

	.lineitem-item {
		background: #f4f4f4;
		padding:  10px;
		border: 1px DarkGrey dotted;
		margin: 2px;
	}

	.is_negative {
		background: #f0ffff;
		padding:  10px;
		border: 1px DarkGrey dotted;
		margin: 2px;
	}

</style>