<script setup>
    const props = defineProps(['valor1', 'valor2', 'filtro'])
</script>
<template>
    <div class="row mt-5">
        <div>
            <input class="form-control text-center" @keyup="props.valor1" type="number" placeholder="Digite um número">
        </div>
        <div class="mt-2 mb-2">
            <input class="form-control text-center" @keyup="props.valor2" type="number" placeholder="Digite mais um número">
        </div>
        <div>
            <select @change="props.filtro" class="form-control text-center">
                <option value="adicao">Adição</option>
                <option value="divisao">Divisão</option>
                <option value="subtracao">Subtração</option>
                <option value="multiplicacao">Multiplicar</option>
            </select>
        </div>
    </div>
</template>