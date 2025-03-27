<script setup lang="ts">

const { modelValue } = defineProps<{ modelValue: boolean }>()
const emit = defineEmits<{
    'update:modelValue': [boolean]
}>()

const handleInput = (event: Event) => {
    emit('update:modelValue', (event.target as HTMLInputElement).checked)
}
</script>

<template>
    <label class="switch">
        <input type="checkbox" :value="modelValue" @input="handleInput" />
        <span class="slider round"></span>
        <div class="icon">
            <i>
                <slot name="iconLeft"></slot>
            </i>
            <i>
                <slot name="iconRight"></slot>
            </i>
        </div>
    </label>
</template>

<style scoped>
.switch {
    position: relative;
    display: inline-block;
    width: 84px;
    height: 44px;
}

/* Hide default HTML checkbox */
.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}

.icon {
    position: absolute;
    display: flex;
    align-items: center;
    width: 80px;
    height: 44px;
    top: 0;
    padding: 4px 8px 4px 8px;
    gap: 12px;
}

i {
    display: flex;
    place-items: center;
    place-content: center;
    width: 28px;
    height: 28px;
    color: var(--color-text);
    cursor: pointer;
}

/* The slider */
.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: .4s;
    transition: .4s;
}

.slider:before {
    position: absolute;
    content: "";
    height: 36px;
    width: 36px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
}

input:checked+.slider:before {
    -webkit-transform: translateX(40px);
    -ms-transform: translateX(40px);
    transform: translateX(40px);
}

/* Rounded sliders */
.slider.round {
    border-radius: 10px;
}

.slider.round:before {
    border-radius: 10px;
}
</style>
