<template>
    <button class='bg-gray-light p-2 rounded-md text-gray-button hover:bg-gray-dark'>
        {{btnText}}
    </button>
</template>

<script>
export default {
    props:['btnText']
}
</script>