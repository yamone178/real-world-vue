<template>
<router-link :to="{name:'detail', params:{id: event.id}}">
  <div class="card mb-3">
    <div class="card-body">
      <h2>{{event.title}}</h2>
      <p>{{event.description}}</p>
    </div>
</div>
</router-link>
  
</template>

<script>
  export default {
    name:'EventCard',
    props: {
     event: Object
    },
    data() {
      return {
       
      }
    },
  }
</script>

<style>

</style>