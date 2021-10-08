<template>
  <section>
    <cabecalho :valor="titulo"/>
    <div class="container">
      <adicionar-tarefa @adicionarTarefa="adicionarTarefa"/>
      <listar-tarefas :tarefas="tarefas"/>
      <div>
        <em>Altere aqui o titulo da sua lista de tarefas:</em>
        <entrada-dados v-model="titulo" type="text" />
      </div>
    </div>
    <rodape/>
  </section>
</template>

<script>
import Cabecalho from '@/components/Cabecalho';
import Rodape from '@/components/Rodape';
import ListarTarefas from './components/ListarTarefas.vue';
import AdicionarTarefa from './components/AdicionarTarefa.vue';
import EntradaDados from '@/components/templates/EntradaDados.vue';
export default {
  name: 'App',
  components: { Cabecalho, Rodape, ListarTarefas, AdicionarTarefa, EntradaDados},
  data() {
    return {
      titulo: "Lista de Tarefas",
      tarefas: [
        {titulo: "Estudar", checked: false},
        {titulo: "Programar", checked: true},
      ]
    };
  },
  methods: {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false,
      });
    },
  },
};
</script>

<style>
body {
  margin: 0px;
}

.container {
  width: 40%;
  margin: 20px auto 0px auto;
}

ul li {
  list-style: none;
}

.removed{
  color: gray;

}

.removed label {
  text-decoration: line-through;
}

</style>