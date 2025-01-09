
<script setup>
    const props = defineProps(["getNumber1", "getNumber2", "getOperator", "result"]);
</script>

<template>
    <form class="text-center">
        <div class="row">
            <div class="col">
                <input type="number" class="form-control mb-4" required placeholder="0" @keyup="props.getNumber1">
            </div>
            <div class="col-md-2 mb-4 text-center">
                <select class="form-control text-center" @change="getOperator">
                    <option value="add" class="add text-center">+</option>
                    <option value="subtract" class="subtract text-center">-</option>
                    <option value="multiply" class="multiply text-center">x</option>
                    <option value="divide" class="divide text-center">÷</option>
                </select>
            </div>
            <div class="col">
                <input type="number" class="form-control" required placeholder="0" @keyup="props.getNumber2">
            </div>
        </div>
        <div class="row">
            <div class="col">
                <h3 class="fw-bold fs-1 ps-2 mb-2">Total: {{ props.result }}</h3>
            </div>
        </div>
    </form>
</template>