<script setup>
import { ref, defineProps } from 'vue'

const props = defineProps({
    addNewTransaction: Function,
})
const transactionText = ref('')
const transactionAmount = ref(0)
</script>
<template>
    <div class="mb-3">
        <div class="text-center">
            <h2>Add new transaction</h2>
            <hr class="m-1">
        </div>
        <form>
        <div class="mb-3">
            <label for="transaction-text" class="form-label">Text</label>
            <input 
                type="text" 
                class="form-control" 
                id="transaction-text"
                v-model="transactionText"
            >
        </div>
        <div class="mb-3">
            <label for="transactionAmount" class="form-label">Amount</label>
            <input 
                type="number" 
                class="form-control" 
                id="transaction-amount"
                v-model="transactionAmount"
            >
            <div id="numberHelp" class="form-text">(negative - expense, positive - income)</div>
        </div>
        <button 
            class="btn btn-primary"
            @click.prevent="props.addNewTransaction(transactionText, transactionAmount)"
        >Add transaction</button>
        </form>
    </div>
</template>
  
