<template>
    <teleport to="body">
        <component
            :is="component"
            @eventBus="eventBus"
        >
        </component>
    </teleport> 
</template>

<script>
import { watch, ref, getCurrentInstance, nextTick, computed } from 'vue'

export default {
    props: ['component']
}
</script>
