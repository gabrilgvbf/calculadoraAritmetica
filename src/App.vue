<script setup>
import { reactive } from 'vue';


const operacao = reactive({
  opcao: '',
  n1: Number(),
  n2: Number(),
  resultado: Number()

}
)


const Aritmetica = () => {

  const { n1, n2, opcao } = operacao



  if (opcao == 'adicao') {

    operacao.resultado = Number(n1) + Number(n2)

  } else if (opcao == 'multiplicacao') {
    operacao.resultado = Number(n1) * Number(n2)
  }
  else if (opcao == 'divisao') {
    operacao.resultado = Number(n1) / Number(n2)
  } else {
    alert('Operaçao não selecionada')
  }


}

</script>

<template>
  <h1>CALCULADO ARITMÉTICA</h1>
  <h3>Escolha a operação</h3>
  <select @change="evento => operacao.opcao = evento.target.value">
    <option value=""></option>
    <option value="multiplicacao">Multiplicação</option>
    <option value="divisao">Divisao</option>
    <option value="adicao">Adição</option>
  </select>
  <div>
    <h3>Digite PRIMEIRO número:</h3>
    <input @change="evento => operacao.n1 = evento.target.value" type="number">

    <h3>Digite SEGUNDO número:</h3>
    <input @change="Aritmetica()" @keyup="evento => operacao.n2 = evento.target.value" type="number">
  </div>
  <div>{{ operacao.resultado }}</div>
</template>

<style scoped></style>
