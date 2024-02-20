<script setup>
import { ref, defineProps, computed } from 'vue'

const props = defineProps({
    addNewTransaction: Function,
})
const transactionText = ref('')
const transactionAmount = ref()
const isFormInvalid = computed(() => {
    return !transactionText.value || !transactionAmount.value
})
const transactionFormRef = ref(null)
const submitForm = (transactionText, transactionAmount) => {
    props.addNewTransaction(transactionText, transactionAmount)
    if (transactionFormRef.value) {
        transactionFormRef.value.reset();
    }
}
</script>
<template>
    <div class="mb-3">
        <div class="text-center">
            <h2>Add new transaction</h2>
            <hr class="m-1">
        </div>
        <form ref="transactionFormRef">
        <div class="mb-3">
            <label for="transaction-text" class="form-label">Text</label>
            <input 
                type="text" 
                class="form-control" 
                id="transaction-text"
                placeholder="Enter text ..."
                v-model="transactionText"
            >
        </div>
        <div class="mb-3">
            <label for="transactionAmount" class="form-label">Amount</label>
            <input 
                type="number" 
                class="form-control" 
                id="transaction-amount"
                placeholder="Enter amount ..."
                v-model="transactionAmount"
            >
            <div id="numberHelp" class="form-text">(negative - expense, positive - income)</div>
        </div>
        <button 
            class="btn btn-primary mb-3"
            @click.prevent="submitForm(transactionText, transactionAmount)"
            :disabled="isFormInvalid"
        >Add transaction</button>
        </form>
    </div>
</template>
  
