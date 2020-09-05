<template>
    <div>
        <h4>CSA A23.3 Equation 1:</h4>
        <p>Note the equation is valid for fc < 45MPa</p>
        <label for="fc">fc = </label>
        <input type="number" min=0 name="fc" v-model="fc1"><span>MPa</span>
        <p>Ec = 4500*sqrt(fc) = 4500*sqrt({{fc1}}) = {{Ec1 | decimalPlaces(1) }} MPa</p>

        <h4>CSA A23.3 Equation 2:</h4>
        <p>Note the equation is valid for all ranges of fc, although it was not developed for ultra-high-strength concretes</p>
        <label for="fc">fc = </label>
        <input type="number" min=0 name="fc" v-model="fc2"><span>MPa</span>
        <br>
        <label for="fc">γc = </label>
        <input type="number" min=0 name="gamma" v-model="gamma"><span>kN/m3</span>
        <p>Ec = (3300*sqrt(fc)+6900)*(γc/2300)^1.5 = (3300*sqrt({{fc2}})+6900)*({{gamma}}/2300)^1.5 = {{Ec2 | decimalPlaces(1) }} MPa</p>
    </div>
</template>

<script>
  export default {
    data () {
      return {
        fc1: 35,
        fc2: 35,
        gamma: 2400,
      }
    },
    computed: {
        Ec1: function() {
            return 4500*Math.sqrt(this.fc1)
        },
        Ec2: function() {
            return (3300*Math.sqrt(this.fc2)+6900)*Math.pow(this.gamma/2300, 1.5)
        }
    }
  }
</script>
