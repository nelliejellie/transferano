<template>
    <button id="bt" class='bg-gray-light p-2 rounded-md text-gray-button hover:bg-gray-dark' v-on:click="doStuff">
        {{btnText}}
    </button>
</template>

<script>
export default {
    props:['btnText'],
    methods:{
        doStuff(e){
            alert(e.target.innerText)
            console.log(e)
            // emit the click event to another component
            this.$emit('handleClick')
        }
    }
}
</script>