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
          `https://app.raspisms.fr/api/scheduled/`,{method:'POST',headers: {'Api-Key': '0cb56244268fac41109d34097af5354b'},body:"{'text':'testfromAPI','groups[]':'1'}"}
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