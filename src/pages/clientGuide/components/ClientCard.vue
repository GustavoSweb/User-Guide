<template>
  <div class="flex flex-col p-3 shadow-xl my-[3em] rounded-lg">
    <div class="max-w-[100%] w-[400px] justify-center flex flex-col">
      <p class="block mb-0 text-[#00000080]" v-if="data.showYear == true">Idade: {{ data.idade }}</p>
      <p v-else class="block mb-0 text-[#00000080]">
        idade: Escondida
      </p>
      <h3>Cliente: {{ data.name }}</h3>
    </div>
    <hr />
    <p>{{ data.descricao }}</p>
    <hr />
    <div class="flex justify-between">
      <small
        >Tel: <span class="text-[#00000080]">{{ data.numero }}</span></small
      >
      <small
        >Email: <span class="text-[#00000080]">{{ data.email }}</span></small
      >
    </div>
  </div>
</template>
<script>

export default {
  name: "Client-Card",
  props: {
   data:Object,
  },
};
</script>
