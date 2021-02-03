<template>
<div>
    MainStage component
    <BlockRoot
        v-for="(c, i) in children"
        :key="i"
        :component="c"
    />
</div>
</template>

<script>
import BlockRoot from "./BlockRoot.vue"

export default {
    props: ['children'],
    components: { BlockRoot }
}
</script>