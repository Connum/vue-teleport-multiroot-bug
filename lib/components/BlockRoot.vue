<template>
    <teleport to="body">
        <component
            :is="component"
        >
        </component>
    </teleport> 
</template>

<script>
export default {
    props: ['component']
}
</script>
