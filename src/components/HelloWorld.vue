<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md">
      <div class="q-gutter-md" style="max-width: 300px">
          <q-input rounded outlined v-model="Number1" type="number" :label="hold1" aria-placeholder=""/>
          <q-btn :loading="loading5" :color="color" @click="Swap(Number1,Number2)" label="Swap" class="btn2"/>
          <q-input rounded outlined v-model="Number2" type="number" :label="hold2" aria-placeholder=""/>
          
      </div>
      <q-btn :loading="loading1" color="red" @click="Everything(Number1,Number2)" label="+" class="btn1" />
      <q-btn :loading="loading2" color="yellow" @click="Multiply(Number1,Number2)" label="*" class="btn1"/>
      <q-btn :loading="loading3" color="blue" @click="Divide(Number1,Number2)" label="÷" class="btn1"/>
      <q-btn :loading="loading4" color="cyan" @click="Subtract(Number1,Number2)" label="-" class="btn1"/>
    <h4>Answer: {{Answer}}</h4>
    
    </div>
    
  </q-page>
</template>



<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      loading1:false,
      loading2:false,
      loading3:false,
      loading4:false,
      loading5:false,
      hold1:"First Number",
      hold2:"Second Number",
      color:"red",
      Number1:"",
      Number2:"",
      Answer:0
    }
  },
  methods: {
    Everything(a,b){
      this.loading1 = true
      
      setTimeout(() => {
        this.loading1 = false
        }, 500)
      this.Answer=Number(a)+Number(b)
    },
    Multiply(a,b){
      this.loading2 = true
      
      setTimeout(() => {
        this.loading2 = false
        }, 500)
      this.Answer=Number(a)*Number(b)
    },
    Divide(a,b){
      this.loading3 = true
      
      setTimeout(() => {
        this.loading3 = false
        }, 500)
      this.Answer=(Number(a)/Number(b)).toFixed(5)
    },
    Subtract(a,b){
      this.loading4 = true
      
      setTimeout(() => {
        this.loading4 = false
        }, 500)
      this.Answer=Number(a)-Number(b)
    },
    Swap(a,b){
      this.loading5 = true
      this.Number1=b
      this.Number2=a
      setTimeout(() => {
        this.loading5 = false
        }, 500)
      this.color="blue"
      
    },
  }

}
</script>



<style scoped>
  .btn1{
    margin: 10px;
    color: aqua;
  }
  
</style>