<template>
  <div class=" w-[100%] md:w-[80%] lg:w-[40%] flex flex-col items-center">
    <h1>Formulario</h1>
    <h2 class="text-[#00000080]">Olá, {{ name }}</h2>
    <div class="w-[100%] flex flex-col gap-2 py-5">
      <label for="name" class="font-semibold text-[20px]">Nome: </label>
      <input
        type="text"
        name="name"
        class="form-control"
        maxlength="10"
        v-model="name"
      />
      <label for="name" class="font-semibold text-[20px]">Email: </label>
      <input type="email" class="form-control" />
      <div class="flex gap-3 my-2">
          <label for="numero" class="font-semibold text-[20px]">Numero: </label>
          <input type="number" name="numero" class="form-control" />
          <label for="idade" class="font-semibold text-[20px]">Idade: </label>
          <input type="number" name="idade" class="form-control" />
      </div>
      <label for="name" class="font-semibold text-[20px]">Descrição: </label>
      <input type="text" class="form-control" />
    </div>
    <button class="btn btn-primary min-w-[50%]">Cadastrar</button>
  </div>
</template>

<script>
export default {
  name: "Client-Form",
  data() {
    return {
      name: "Usuario",
      numero: "",
      email: "",
      idade: "",
      descricao: "",
    };
  },
};
</script>