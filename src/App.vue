<template>
	<div class="container">
		<HeaderComponent />
		<HistoryComponent />
		<AddTransactionForm />
	</div>

</template>

<script setup>
import HeaderComponent from './components/HeaderComponent.vue'
import HistoryComponent from './components/HistoryComponent.vue'
import AddTransactionForm from './components/AddTransactionForm.vue'
</script>

<style>
#app {
	background-color: whitesmoke;
}

.container{
        max-width: 770px;
}
</style>
