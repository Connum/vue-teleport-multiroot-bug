<template>
<div>
    MainStage component
    <BlockRoot
        v-for="(c, i) in children"
        :key="i"
        :component="c"
        @eventBus="eventBus"
    />
</div>
</template>

<script>
import BlockRoot from "./BlockRoot.vue"

export default {
    props: ['children'],
    components: { BlockRoot },
    setup(props, { emit }) {    
        const eventBus = (data) => emit('eventBus', data)

        return {
            eventBus,
        }
    }
}
</script>