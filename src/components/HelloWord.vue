<template>
    <div>
        {{ friend }}
        <button @click="emit('update','Tran Bao Giang')">emit</button>
    </div>
</template>
<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';
defineProps({
    friend: {
        type: String,
        required: true
    }
})

const emit = defineEmits(['update'])


</script>