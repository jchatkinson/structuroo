<template>
    <div>
        <p>Parent Component</p>
        <Steel-Child1 :value="parentvalue" v-on:test-event="logEvent($event)" />
    </div>
</template>

<script>
  export default {
    data () {
      return {
          parentvalue: 1.0
      }
    },
    computed: {

    },
    methods: {
        logEvent(value) {
            console.log(`test event heard by parents v-on. The value was ${value}`)
        }
    }
  }
</script>
