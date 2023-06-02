<script setup>
  import { reactive } from 'vue';

 
  const  estado = reactive({ 
    calculos: 
    [
    {
      numero1: '',
      numero2: '',
      // titulo: 'Mutiplicação:',
      // calcularMultiplicacao:  numero1 * numero2, 
    },
    // {
    //   titulo: 'Subtração:',
    //   // calcularSubtracao: numero1 - numero2,
    // },
    // {
    //   titulo: 'Divisão:',
    //   // calcularDivisao: numero1 / numero2,
    // },
    ]
  })
  function calcularMultiplicacao() {
const { numero1, numero2 } = estado;
  return Number (numero1) * Number (numero2);
}
function calcularSubtracao(){
const { numero1, numero2 } = estado;
return Number (numero1) - Number (numero2);
}
function calcularDivisao(){
const { numero1, numero2 } = estado;
return Number (numero1) / Number (numero2);
}
function calcularAdicao(){
const { numero1, numero2 } = estado;
return Number (numero1) + Number (numero2);
}
</script>

<template>
  <div class="container">
    <header class="p-5">
      <h1>Calculadora Aritmética</h1>
    </header>
    <form>
      <div class="row " >
        <div class=" col-md-3 text-center ">
              <!-- <select class="form-control m-1" >
            <option>Escolha a operação</option>
            <option value="subtracao" @click="calcularSubtracao">Subtração</option>
            <option value="multiplicacao"  @click="calcularMultiplicacao" >Multiplicação</option>
            <option value="divisao" @click="calcularDivisao">Divisão</option>
            <option value="adicao" @click="calcularAdicao">Adição</option>
          </select> -->
        </div>
        <div class="col-md-6 d-flex mb-5" >
          <input @keyup="evento => estado.numero1 = evento.target.value" class="form-control m-1" />
          <input  @keyup="evento => estado.numero2 = evento.target.value" class="form-control m-1" />  
        </div>
      </div>
    </form>
    <!-- <ul class="list-group mt-4">
      <li class="list-group-item"  v-for="calculo in estado.calculos ">
        <label class="ms-3" >
          {{ calculo.titulo }} 
          {{ calculo.calcularMultiplicacao }}
          {{ calculo.calcularSubtracao }}
          {{ calculo.calcularDivisao }}
          {{  estado.numero1 * estado.numero2  }} 
        </label>
      </li>
    </ul> -->
          Multiplicação: {{ calcularMultiplicacao() || 0 }} <br>
          Subtração: {{ calcularSubtracao() || 0 }} <br>
          Divisão: {{ calcularDivisao() || 0 }} <br>
          Adição: {{ calcularAdicao() || 0 }} <br>
  </div>
</template>

<style>
.container {
  width: 100%;
  text-align: center;
  color: brown;
  font-size: 26px;
}h1{
  letter-spacing: 11px;
}
/* @media screen and (min-width:769px) and (max-width:1024px){
   .container{
    width: 100%;
   }

} */
</style>
