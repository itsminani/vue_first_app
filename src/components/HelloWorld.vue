<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md">
      <div class="q-gutter-md" style="max-width: 300px">
          <q-input rounded outlined v-model="Number1" label="First Number" aria-placeholder=""/>
          <q-input rounded outlined v-model="Number2" label="Second Number" aria-placeholder=""/>
          <q-btn :loading="loading1" :color="color" @click="Everything(Number1,Number2)" label="Button" />
          <h4>Answer: {{Answer}}</h4>
      </div>
    </div>
  </q-page>
</template>



<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      loading1:false,
      color:"red",
      Number1:"",
      Number2:"",
      Answer:0
    }
  },
  methods: {
    Everything(a,b){
      this.loading1 = true
      this.color="blue"
      setTimeout(() => {
        this.loading1 = false
        }, 1000)
      this.Answer=Number(a)+Number(b)
    } 
  },
}
</script>
