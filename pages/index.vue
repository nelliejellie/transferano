<template>
  <section class="bg-gray-light">
    <div class='h-24 w-auto bg-gray-dark'></div>
    <div class="w-full flex flex-row justify-center focus-within:text-gray-600 ">
       <input class="h-12 w-2/4 border-white rounded-md -mt-6 p-6 text-gray-dark focus-within:border-white"
        placeholder="search by role" v-model="search" type="text"
       /> 
    </div>
    <div class='w-auto h-auto m-2' >
      <Person v-for="peeps in filteredPeople" :key="peeps.id"
        :objectData="peeps"
      />
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return {
      people:[],
      search:''
    }
  },
  mounted(){
    fetch('http://localhost:8000/people')
      .then(res => res.json())
      .then(data => {this.people = data})
      .catch(err => console.log(err.message))
  },
  computed:{
    filteredPeople(){
      return this.people.filter((peeps)=>{ 
        return peeps.role.match(this.search)
      })
    }
  }
}
</script>

<style>

</style>