<template>
  <div
    class="flex px-2 pt-[100px] flex-col items-cemter lg:items-start lg:flex-row lg:justify-around min-h-[100vh]"
  >
    <ClientForm :CadastrarUsuario="CadastrarUsuario"/>
    <div class="lg:flex lg:flex-col">
      <div v-for="(cliente, index) in Clients" :key="cliente.id">
        <div
          class="rounded-lg shadow-lg max-w-[100px] min-h-[30px] py-1 px-2 flex justify-center"
        >
          Index: {{ index + 1 }}
        </div>
        <ClientCard :data="cliente" />
      </div>
    </div>
  </div>
</template>
<script>
import ClientForm from "./components/ClientForm";
import ClientCard from "./components/ClientCard";
import ValidateForm from '../../utils/ValidateForm'
export default {
  name: "Client-Guide",
  data() {
    return {
      Clients: [
        {
          id: 1,
          descricao:
            "Moro em Buique-PE sou estudante da ete jornalista cyl gallindo",
          name: "Gustavo",
          email: "gustavodasilvama10@gmail.com",
          telefone: 5587999170852,
          idade: "17",
          showYear: false,
        },
        {
          id: 2,
          descricao:
            "Moro em Buique-PE sou estudante da ete jornalista cyl gallindo",
          name: "Vitor",
          email: "gustavodasilvama10@gmail.com",
          telefone: 5587999170852,
          idade: "17",
          showYear: true,
        }
      ],
    };
  },
  components: {
    ClientForm,
    ClientCard,
  },
  methods: {
    CadastrarUsuario: async function (data) {
      try{
        let dataProcess = new ValidateForm(data)
        dataProcess.Check()
      this.Clients.push(dataProcess);
      return false
      }catch(err){
        return err.message
      }
    },
  },
};
</script>