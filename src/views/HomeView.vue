<script setup lang="ts">
import Form from '@/components/Form.vue'
import { ref } from 'vue'

const name = ref<string>('')

const handleReset = (value: string) => {
    name.value = value
}

const handleClick = () => {
    name.value = 'reset'
}
</script>

<template>
    <h2>Parent Component</h2>
    <div class="grid">
        <div>
            <button @click="handleClick">Reset Input from Parent</button>
        </div>
        <div>
            <Form
                :reset-name-value="name"
                @reset-input="handleReset"
            />
        </div>
    </div>
</template>

<style scoped>
.grid {
    margin-top: 20px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    gap: 20px;
    align-items: center;
    justify-content: center;
}
</style>
