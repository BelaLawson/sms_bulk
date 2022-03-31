<template>
    
</template>
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      try {
        const result = fetch(
          `http://192.168.0.17/rapisms/`,{method:'POST', mode: 'no-cors', headers: {'X_API_KEY': '0cb56244268fac41109d34097af5354b','Accept': 'application/json','Content-Type': 'application/json'},body:"{'text':'testfromAPI','groups[]':'1'}"}
        )
        if (result.status === 200) {
          const body = result.json()
          console.log(body)
        }
      } catch (e) {
        console.error('Error->', e)
      }
    }
  },
  mounted() {
    // methods can be called in lifecycle hooks, or other methods!
    this.increment()
  }
}
</script>