<template>
  <div class="home">

    <div class="container">
      <div class="row">
        <div class="col-6">
           <EventCard v-for="event in events" :key="event.id" :event="event"/>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from '@/components/EventCard.vue';
import EventService from '../services/EventService.js'
export default {
  name: 'EventList',
  components: {
    EventCard
  },

  data() {
    return {
      events: null
    }

  },
  created() {
    EventService.getEvents().then(response=>{
      this.events= response.data
      
    }).catch(error=>{
      console.log(error)
    })

  },
}
</script>

<style>

</style>
