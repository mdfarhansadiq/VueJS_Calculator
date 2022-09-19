<template>
    <div>
        <h1>{{title}}</h1>
    </div>
    <PButton/>
</template>



<script>
    import PButton from './ProjectButton.vue';
    export default{
        name: 'PHeader',
        props:{
            title: String
        },
        components:{
            PButton
        }
    }
</script>