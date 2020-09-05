<template>
    <div>
        <p>the value is {{value}}</p>
        <button v-on:click="$emit('test-event', cValue)">Emit an event</button>
    </div>
</template>

<script>
  export default {
    props: ['value'],
    data () {
      return { 
          cValue: 2
        }
    },
    computed: {

    },
    methods: {

    }
  }
</script>
