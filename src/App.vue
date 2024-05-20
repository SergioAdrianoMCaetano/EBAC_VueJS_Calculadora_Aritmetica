<!-- A entrega deste exercício consiste em:

• Criar um projeto utilizando VueJS;

• Este projeto será uma calculadora aritmética;

• Deverá conter dois campos para inserir os números;

• Um campo do tipo select para escolher a operação aritmética;

• Ao alterar os valores o cálculo já deverá ser realizado, sem precisar clicar em nenhum botão;

• Crie um repositório no Github para esta tarefa e nos envie o link pela plataforma.  -->

<script setup>
  import { reactive, computed } from 'vue';
  //Objeto reativo
  const estado = reactive({
    num1: 0,
    num2: 0,
    operacao: 'somar',
  });
  //Propriedades para calcular o resultado
  const resultado = computed(()=>{
    switch (estado.operacao) {
      case 'somar':
        return estado.num1 + estado.num2
      case 'subtrair':
        return estado.num1 - estado.num2
      case 'multiplicar':
        return estado.num1 * estado.num2  
      case 'dividir':
        return estado.num2 !== 0 ? estado.num1 / estado.num2 : 'Erro: Divisão por zero';
      default:
        return 0;
    }
  });
  //Função para determinar o símbolo da operação
  const simboloOperacao = computed(()=>{
    switch(estado.operacao){
      case 'somar':
        return '+';
      case 'subtrair':
        return '-';
      case 'multiplocar':
        return '*';
      case 'dividir':
        return '/';
      default:
        return '';
    }
  });

</script>

<template>
  <!--CABECALHO-->
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-cabecalho rounded-3">
      <h1>Calculadora Aritmética</h1>
      <p>
        O resultado de {{estado.num1}} {{ simboloOperacao }} {{ estado.num2}}  é igual a {{ resultado }}
      </p>
    </header>
    <!--CAMPOS PARA INSERIR NÚMEROS-->
    <div class="calculadora">
      <input v-model.number="estado.num1" placeholder="Primeiro número" type="number" class="m-5">
      <input v-model.number="estado.num2" placeholder="Segundo número" type="number"  class="m-5">
      <select v-model="estado.operacao">
        <option value="somar"> + </option>
        <option value="subtrair"> - </option>
        <option value="multiplicar"> * </option>
        <option value="dividir"> / </option>
      </select>
      <p class="resultado m-2"><strong>Resultado: </strong>{{ resultado }}</p>
    </div>
  </div>
</template>

<style scoped>

  body{
    background-color: aqua
  }
  
  .bg-cabecalho{
      background-color: #185ABD;
      color: #fff;
  }

  .calculadora{
    display: flex;
    flex-direction: column;
    text-align: left;
    align-items: center;
  }
  
    .resultado{
      font-size: 20px;
      font-weight: bold;
    }

  input, select{
    display: block;
    margin: 10px 0;
    padding: 10px;
    font-size: 16px;
    text-align: center;
  }

  select{
    width: 5%;
    height: 10%;
  }


</style>
