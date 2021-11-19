<template>
    <div class="w-full flex flex-row justify-center focus-within:text-gray-600 ">
       <input class="h-12 w-2/4 border-white rounded-md -mt-6 p-6 text-gray-dark focus-within:border-white"
        placeholder="search" v-model="search" type="text"
       /> 
    </div>
</template>
<script>
export default {

}
</script>
<style>
    input:focus{
        outline: none;
    }
</style>