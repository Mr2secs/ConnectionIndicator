<template>
<div @dragover="allowDrop" @drop="onDrop(exchange)">
    <v-chip-group selected-class="text-primary" column>
        <v-chip draggable   @dragstart="draggedData=exchange"  v-for="exchange in exchanges" :key="exchange">
            {{ exchange }}
        </v-chip>
    </v-chip-group>
    {{chip}}
</div>
</template>

<script>
export default {
    props: [
        'exchanges'
    ],
    data() {
        return {
            chip: 'test'
        }
    }, 
    methods: {
        onDrop() {
            this.chip = this.draggedData;
        },
        allowDrop(e) {
            e.preventDefault();
        }
    },
    
}
</script>