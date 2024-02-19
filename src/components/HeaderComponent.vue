<template>
    <div class="expense-tracker">
        <h1 class="title">Expense Tracker</h1>
        <h2 class="subtitle">YOUR BALANCE</h2>
        <h1 class="balance positive">500 €</h1>
    
        <div class="row">
            <div class="col">
                <div class="card">
                    <div class="card-body d-flex flex-column justify-content-center align-items-center">
                        <h5 class="card-title">INCOME</h5>
                        <h1 class="positive">+ 500 €</h1>
                    
                    </div>
                </div>
            </div>
            <div class="col">
                <div class="card">
                    <div class="card-body d-flex flex-column justify-content-center align-items-center">
                        <h5 class="card-title">EXPENSE</h5>
                        <h1 class="negative">- 290 €</h1>                
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script setup>
</script>
  
<style>
.expense-tracker {
    text-align: center;
    margin: 20px auto;
    padding: 20px;
}
  
.title {
    font-size: 24px;
    margin-bottom: 10px;
}
  
.subtitle {
    font-size: 18px;
    color: #666;
    margin-bottom: 10px;
}
  
.balance {
    font-size: 36px;
    margin-top: 10px;
}

.positive {
    color: #2ecc71;
}
.negative {
    color: #e74c3c;
}
</style>
  