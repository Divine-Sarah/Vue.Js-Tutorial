<template>
    <ul>
        <Item v-for="video in videos" v-bind:key="video.id"
         v-bind:video="video">Video</Item>
    </ul>
</template>

<script>
    import Item from "./item.vue";
    export default {
        // eslint-disable-next-line vue/multi-word-component-names
        name: "Videos",
        props:["videos"],
        components: {
            Item, 
        },
    };
</script>

<style >

</style>
