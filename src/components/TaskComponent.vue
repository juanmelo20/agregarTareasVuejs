<script setup>

const props = defineProps({
    name: {
        type: String,
        default: '-'
     },
    index: {
    type:Number
    }
})
const emit = defineEmits([
    'deleteTask'
])
const deleteTask =(index)=>{
    emit('deleteTask',index)
}
</script>
<template>
    <div class="flex justify-between px-4 py-2 
    bg-gray-200 rounded">
    {{ props.name }}
        <span @click="deleteTask(props.index)" class="inline-block px-2 text-white
        bg-red-800 rounded hover:bg-red-400 hover:cursor-pointer">
            x
        </span>
    </div>
</template>