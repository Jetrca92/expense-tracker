<script setup>
import HeaderComponent from './components/HeaderComponent.vue'
import HistoryComponent from './components/HistoryComponent.vue'
import AddTransactionForm from './components/AddTransactionForm.vue'
import { ref } from 'vue'

const transactionsList = ref([
	{ text: "Salary", amount: 1650 }
])
const userBalance = ref(1650)
const userIncome = ref(1650)
const userExpense = ref(0)
// Work in progress
const addNewTransaction = (transactionText, transactionAmount) => {
	transactionsList.value.push({ text: transactionText, amount: transactionAmount })
	if (transactionAmount > 0) {
		userIncome.value += transactionAmount
		
	} else {
		userExpense.value += transactionAmount
	}
	userBalance.value += transactionAmount
}
</script>

<template>
	<div class="container">
		<HeaderComponent 
			:userBalance="userBalance"
			:userIncome="userIncome"
			:userExpense="userExpense"
		/>
		<HistoryComponent 
			:transactionsList="transactionsList"
		/>
		<AddTransactionForm 
			:addNewTransaction="addNewTransaction"
		/>
	</div>

</template>

<style>
#app {
	background-color: whitesmoke;
}

.container{
    max-width: 770px;
}
</style>
