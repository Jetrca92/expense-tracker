<script setup>
import { defineProps } from 'vue'

const props = defineProps({
    transactionsList: Array,
})
</script>

<template>
    <div class="text-center mb-3">
        <h2>History</h2>
        <hr class="m-1">
        <ul class="list-group">
            <li 
                class="list-group-item mb-1 d-flex justify-content-between p-0"
                v-for="(transaction, index) in props.transactionsList"
                :key="index"
            >
                <div class="p-2">
                    {{ transaction.text }}
                </div>
                <div class="p-2">
                    {{ transaction.amount }} €
                </div>
                <div 
                    class="px-1"
                    :class="transaction.amount >= 0 ? 'px-1 bg-positive' : 'px-1 bg-negative'"
                ></div>
            </li>
        </ul>
    </div>
</template>
  
<style>
.bg-positive {
    background-color: #2ecc71;
}
.bg-negative {
    background-color: #e74c3c;
}
</style>
  