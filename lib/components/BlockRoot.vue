<template>
    <teleport to="body">
        <component
            :is="component"
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
