<template>

  <div class="pa-4">

     <v-img
      contain
      class="mt-2 mb-4"
      src="img/Busdoor.png"
    />

    <v-card class="pl-3 pr-2 pt-3 pb-1 mb-4" style="background: #ff9999">
      <p><b>ATENÇÃO!</b> Certifique-se que as informações estão corretas, pois serão conferidas antes do embarque do ônibus pelo responsável. <b>Boa diversão!</b></p>
    </v-card>

    <v-text-field
      filled  
      label="Nome Completo"
      v-model="whats.nome"
    ></v-text-field>

    <v-text-field
      filled  
      label="Número com DDD"
      v-model="whats.telefone"
      v-mask="'(##) #####-####'"
    ></v-text-field>

    <v-text-field
      filled  
      label="Quantidade de passageiros"
      v-model="whats.passageiros"
      type="number"
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
      class="mt-0"
    ></v-checkbox>

    <v-checkbox
      v-model="whats.instagram"
      label="curtiu nossa página do instagram?"
      color="orange"
      hide-details
      class="mt-0"
    ></v-checkbox>

    <v-btn
      x-large
      color="orange"
      class="mt-2"
      dark
      style="width: 100%;"
      target="_blank"
      @click="enviarWhats()"

    >Receber ticket</v-btn>
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
        passageiros: null,
        regiao: null,
        is_cliente: false,
        instagram: false,
      },

      regioes: [
        'Dourados', 'Itaporã', 'Montese', 'Piraporã', 'Santa terezinha', 'Carumbé'
      ]
    }
  },

  methods: {
    enviarWhats(){
      window.location.href=`https://api.whatsapp.com/send?phone=556791708000&text=*Diversão garantida!* %0A *TICKET*:${Math.floor(Math.random()* 1000000) + 3} %0A *Nome*: ${this.whats.nome} %0A *Telefone*: ${this.whats.telefone} %0A *Região*: ${this.whats.regiao} %0A *cliente master?* ${this.whats.is_cliente} %0A *curtiu a página?* ${this.whats.instagram} %0A *qtde. passageiros: * ${this.whats.passageiros}`
    }
  }
}
</script>