<template>
    <div class="mb-3">
        <div class="text-center">
            <h2>Add new transaction</h2>
            <hr class="m-1">
        </div>
        <form>
        <div class="mb-3">
            <label for="text" class="form-label">Text</label>
            <input type="text" class="form-control" id="text">
        </div>
        <div class="mb-3">
            <label for="amount" class="form-label">Amount</label>
            <input type="number" class="form-control" id="number">
            <div id="numberHelp" class="form-text">negative - expense, positive - income</div>
        </div>
        <button type="submit" class="btn btn-primary">Add transaction</button>
        </form>
    </div>
</template>
  
<script setup>
</script>