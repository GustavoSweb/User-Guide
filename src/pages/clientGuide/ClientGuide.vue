<template>
  <div
    class="flex px-2 pt-[100px] flex-col items-center lg:items-start lg:flex-row lg:justify-around min-h-[100vh]"
  >
    <ClientForm />
    <div class="lg:flex lg:flex-col">
      <ClientCard :data="dataClient" />
      <ClientCard :data="dataClient" />

    </div>
  </div>
</template>
<script>
import ClientForm from "./components/ClientForm";
import ClientCard from "./components/ClientCard";

export default {
  name: "Client-Guide",
data(){
    return{
        dataClient:{
            descricao: 'Moro em Buique-PE sou estudante da ete jornalista cyl gallindo',
            name: 'Gustavo',
            email: 'gustavodasilvama10@gmail.com',
            numero: '+55 (87) 9 9917-0852',
            idade: '17',
        }
    }
},
  components: {
    ClientForm,
    ClientCard,
  },
};
</script>