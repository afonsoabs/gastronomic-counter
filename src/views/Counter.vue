<template>
    
    <div class="d-flex align-center justify-center flex-column pa-4">

      <v-img
        contain
        class="mt-2 mb-8"
        src="img/Busdoor.png"
      />
      <div class="mb-4">
        <div  class="d-flex align-center mb-4">
          <v-btn color="orange" x-large style="width: 50%;" @click="counter_meth()" class="mr-2">
            <v-icon size="30" color="white">
              mdi-plus
            </v-icon>
          </v-btn>

          <v-btn color="orange" style="width: 50%;" x-large @click="counter_meth_negative()">
            <span style="color: white; font-size: 3rem; font-weight: bold">-</span>
          </v-btn>
        </div>

        <v-btn x-large style="width: 100%; font-size: 1rem" color="orange" class="ml-1" dark @click="reset()">
        reset
        </v-btn>
      </div>

      <span class="mt-9 font-weight-bold"
      style="font-size: 9rem; color: orange;">
        {{this.counter}}
      </span>
    </div>
</template>

<script>
export default {
    name: 'Counter',

    data: ()=>{
        return{

          counter: 0,
        }
    },

    methods: {
      counter_meth(){
        this.counter = this.counter + 1;
      },

      counter_meth_negative(){
        this.counter = this.counter - 1;
      },

      reset(){
        this.counter = 0;
      }
    }
}
</script>