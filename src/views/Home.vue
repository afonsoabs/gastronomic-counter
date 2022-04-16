<template>

  <div class="pa-4">
    <v-text-field
      filled  
      label="Nome Completo"
      v-model="whats.nome"
    ></v-text-field>

    <v-text-field
      filled  
      label="Número com DDD"
      v-model="whats.telefone"
    ></v-text-field>

    <v-autocomplete
      v-model="whats.regiao"
      :items="regioes"
      dense
      filled
      label="Região"
    ></v-autocomplete>

    <v-checkbox
      v-model="whats.is_cliente"
      label="cliente Master?"
      color="orange"
      hide-details
    ></v-checkbox>

    <v-btn
      x-large
      color="orange"
      class="mt-4"
      style="width: 100%;"
      target="_blank"
      @click="enviarWhats()"

    >Enviar dados</v-btn>
  </div>

</template>

<script>
export default {
  name: 'Home',

  data: ()=>{

    return{

      whats: {
        nome: null,
        telefone: null,
        regiao: null,
        is_cliente: false,
      },

      regioes: [
        'Dourados', 'Montese', 'Piraporã', 'Santa terezinha', 'Carumbé'
      ]
    }
  },

  methods: {
    enviarWhats(){
      window.location.href=`https://api.whatsapp.com/send?phone=5508006471195&text=nome: ${this.whats.nome} \n telefone: ${this.whats.telefone} \n  região: ${this.whats.regiao} \n cliente master? ${this.whats.is_cliente}`
    }
  }
}
</script>