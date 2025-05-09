<script setup>
defineProps({
    operacao: { type: String },
});

const emit = defineEmits(['update:operacao']);
</script>

<template>
    <div class="row mt-2 justify-content-md-center">
        <div class="col-4">
            <select :value="operacao" @change="emit('update:operacao', $event.target.value)"
                class="form-control text-center btn btn-warning fw-bold">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
        </div>
    </div>
</template>