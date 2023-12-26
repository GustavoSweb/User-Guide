<template>
  <div class="flex px-2 pt-[100px] flex-col items-center lg:items-start lg:flex-row lg:justify-around min-h-[100vh]">
    <ClientForm />
    <div  class="lg:flex lg:flex-col">
      <div v-for="cliente in Clients" :key="cliente.id"><ClientCard :data="cliente"/></div>
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
  numero: '+55 (87) 9 9917-0852',
  idade: '17',
  showYear: false
}, {
  id: 2,
  descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
  name: 'Gustavo',
  email: 'gustavodasilvama10@gmail.com',
  numero: '+55 (87) 9 9917-0852',
  idade: '17',
  showYear: true
}, {
  id: 3,
  descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
  name: 'Gustavo',
  email: 'gustavodasilvama10@gmail.com',
  numero: '+55 (87) 9 9917-0852',
  idade: '17',
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