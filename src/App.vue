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
	updateUserBalance(transactionAmount, true)
}
const deleteTransaction = (index) => {
	updateUserBalance(transactionsList.value[index].amount)
	const updatedTransactionsList = transactionsList.value.filter((item, i) => i !== index);
    transactionsList.value = updatedTransactionsList;
}
const updateUserBalance = (transactionAmount, isAddingTransaction) => {
	if (transactionAmount > 0) {
		userIncome.value += isAddingTransaction ? transactionAmount : -transactionAmount
	} else {
		userExpense.value += isAddingTransaction ? -transactionAmount : +transactionAmount
	}
    userBalance.value += isAddingTransaction ? transactionAmount : -transactionAmount
};
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
			:deleteTransaction="deleteTransaction"
		/>
		<AddTransactionForm 
			:addNewTransaction="addNewTransaction"
		/>
	</div>

</template>

<style>

.container{
    max-width: 770px;
	background-color: whitesmoke; 
    border: 1px solid #ccc;
    padding: 20px;
}
</style>
