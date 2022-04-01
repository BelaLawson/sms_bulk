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
    async increment() {
      try {
        const result = await fetch(
          `/raspismsyo`,{method:'POST', mode: 'cors', headers: {'X-Api-Key': '98caa922901991664a0482d772f056cc','Accept': 'application/json','Content-Type': 'application/json', 'text':"44jjjnf",'groups':'1'}, body: JSON.stringify({text:"testfromAPI",groups:"1"})}
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