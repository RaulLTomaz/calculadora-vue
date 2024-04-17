<script setup>
    const props = defineProps(["defineNum1", "defineNum2", "mudaResultado"])
</script>

<template>
    <div class="col">
        <label>Numero 1:</label>
        <input value="0" @change="$props.defineNum1" type="number">
    </div>
    <div class="col">
        <label>Numero 2:</label>
        <input value="0" @change="$props.defineNum2" type="number">
    </div>
    <div class="col-md-2">
        <label>Operação:</label>
        <select @change="$props.mudaResultado" class="form-control">
            <option value="default">Escolha</option>
            <option value="soma">Soma</option>
            <option value="subtracao">Subtração</option>
            <option value="multi">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>
    </div>
</template>

<style scoped>
    input {
        width: 100%;
        height: 38px;
        border-radius: 3px;
    }
</style>