<script setup lang="ts">
import type { Props, SubmitAction } from '@/types'
import { ref, watch } from 'vue'

const name = ref<string>('')

const emit = defineEmits<{
    resetInput: [value: SubmitAction]
}>()

const props = withDefaults(defineProps<Props>(), {
    resetNameValue: '',
})

watch(
    () => props.resetNameValue,
    (newValue) => {
        if (newValue === 'reset') {
            name.value = ''
            emit('resetInput', '')
        }
    },
)
</script>

<template>
    <div class="child">
        <h2>Child Component</h2>

        <form>
            <label>
                Enter your name:
                <input
                    v-model="name"
                    type="text"
                    maxlength="15"
                />
            </label>
        </form>

        <p
            v-if="name"
            class="para"
        >
            Hello, {{ name }}!
        </p>
    </div>
</template>

<style scoped>
.child {
    background-color: #f0f0f0;
    padding: 20px;
    border-radius: 8px;
    margin-top: -60px;
    min-height: 150px;
}
.para {
    margin-top: 10px;
    height: 30px;
}
</style>
