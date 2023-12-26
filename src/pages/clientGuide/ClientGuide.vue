<template>
  <div class="flex px-2 pt-[100px] flex-col items-cemter lg:items-start lg:flex-row lg:justify-around min-h-[100vh]">
    <ClientForm />
    <div  class="lg:flex lg:flex-col">
      <div v-for="(cliente, index) in Clients" :key="cliente.id"><div class="rounded-lg shadow-lg max-w-[100px] min-h-[30px] py-1 px-2 flex justify-center">Index: {{ index + 1 }}</div><ClientCard :data="cliente"/></div>
    </div>
  </div>
</template>
<script>
import ClientForm from "./components/ClientForm";
import ClientCard from "./components/ClientCard";
var Clients = [{
  id: 1,
  descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
  name: 'Gustavo',
  email: 'gustavodasilvama10@gmail.com',
  numero: 5587999170852,
  idade: '17',
  showYear: false
}, {
  id: 2,
  descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
  name: 'Vitor',
  email: 'gustavodasilvama10@gmail.com',
  numero: 5587999170852,
  idade: '17',
  showYear: true
}, {
  id: 3,
  descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
  name: 'Jose',
  email: 'gustavodasilvama10@gmail.com',
  numero: 5587999170852,
  idade: 17,
  showYear: false
}]
export default {
  name: "Client-Guide",
  data() {
    return {
      Clients
    }
  },
  components: {
    ClientForm,
    ClientCard,
  },
};
</script>