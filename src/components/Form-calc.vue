<script setup>
defineProps({
    numero1: { type: [Number, String] },
    numero2: { type: [Number, String] },
});

const emit = defineEmits(['update:numero1', 'update:numero2']);
</script>

<template>
    <div class="row mt-5 justify-content-md-center">
        <div class="col-2">
            <input :value="numero1" @input="emit('update:numero1', $event.target.value)" class="form-control"
                type="number" required />
        </div>
        <div class="col-2">
            <input :value="numero2" @input="emit('update:numero2', $event.target.value)" class="form-control"
                type="number" required />
        </div>
    </div>
</template>