<template>
    <div>
        <div
            :style="{'margin-left': `${depth*20}px`}"
            class="node">
            <h1>{{node.name}}</h1>
        </div>
        <TreeBrowser 
          v-for="child in node.children"
          :key="child.name"
          :node="child"
          :depth="depth + 1"
        />
    </div>
</template>

<script>
export default {
    name: 'TreeBrowser',
    props: {
        node: Object,
        depth: {
            type: Number,
            default: 0,
        }
    }
}
</script>

<style scoped>
    .node {
        text-align: left;

    }
</style>
