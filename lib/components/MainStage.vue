<template>
<div>
    MainStage component
    
    <teleport to="body"
        :key="i"
        v-for="(c, i) in children">
        <SingleRootBLock v-if="c === 'single'" />
        <MultiRootBLock v-if="c === 'multi'" />
    </teleport> 
</div>
</template>

<script>
import SingleRootBLock from '/lib/blocks/SingleRootBlock.vue'
import MultiRootBLock from '/lib/blocks/MultiRootBlock.vue'

export default {
    props: ['children'],
    components: { SingleRootBLock, MultiRootBLock }
}
</script>