<template>
    
    <div class="d-flex align-center justify-center flex-column pa-4">

      <div class="mb-4">
        <v-btn color="orange" @click="counter_meth()" class="mr-3">
          <v-icon>
            mdi-plus
          </v-icon>
        </v-btn>

        <v-btn color="orange" @click="reset()" >
        reset
        </v-btn>
      </div>

      <span class="mt-4">
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

      reset(){
        this.counter = 0;
      }
    }
}
</script>