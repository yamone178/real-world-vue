<template>
    <div v-if="event">

        <h4>{{event.title}}</h4>
        <p>{{event.description}}</p>

    </div>
</template>

<script>
import EventService from '../services/EventService.js'

    export default {
        props: ['id'],
       data() {
    return {
      event: null,
      
    }

  },
  created() {
    EventService.getEventsDetail(this.id).then(response=>{
      this.event= response.data
      
    }).catch(error=>{
      console.log(error)
    })

  },
    }
</script>

<style lang="scss" scoped>

</style>