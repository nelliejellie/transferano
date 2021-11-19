<template>
    <div>
    <div class="person-div h-36 w-9/12 m-auto bg-gray-lightest border-white mt-16 rounded-md flex flex-row justify-around  shadow-lg  hover:border-gray-dark border-l-2"
    >
        <img :src="objectData.logo" class='m-2 rounded-full'>
        <div class="p-p flex flex-col flex-grow m-1 justify-center">
            <p class="text-gray-button font-bold capitalize">{{objectData.company}}</p>
            <p class="text-gray-button font-bold capitalize">{{objectData.position}}</p>
            <p class='flex flex-row justify-around w-48 text-gray'><span>{{objectData.postedAt}}</span><span>{{objectData.contract}}</span><span>{{objectData.location}}</span></p>
        </div>
        <div class="flex flex-row flex-grow m-2 justify-around items-center button"> 
            <Button :btnText="objectData.role" />
            <Button :btnText="objectData.level" />
            <Button v-for="lang in objectData.languages" :btnText="lang" :key="lang"/>
        </div>
    </div>
    </div>
</template>
<script>
export default {
    props:['objectData']
}
</script>
<style scoped>
    @media (max-width: 425px){
        .person-div{
            height: 28vh;
            margin-top: 4vh;
            padding-left: 4vw;
            padding-right: 4vw;
            flex-direction: column;
            justify-content: space-between;
        }
        .p-p{
            justify-content: flex-start;
        }
        img{
            margin-top:-2vh ;
            width: 10vw;
            height: 5vh;
        }
        .button{
            flex-wrap: wrap;
            border-top: 1px solid black;

        }
    }
</style>