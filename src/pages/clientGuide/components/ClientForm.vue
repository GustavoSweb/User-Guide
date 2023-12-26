<template>
  <div class="w-[100%] md:w-[80%] lg:w-[40%] flex flex-col items-center">
    <div class="flex flex-col lg:flex-row items-center lg:justify-between w-full">
      <div class="flex flex-col ">
        <h1>Formulario</h1>
        <h2 class="text-[#00000080]">Olá, {{ name }}</h2>
      </div>
      <div :class="['alert','alert-warning','mt-3', {'hidden': !isError, 'block' : isError}]" role="alert">
        <svg
          class="flex-shrink-0 inline w-4 h-4 me-3"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="currentColor"
          viewBox="0 0 20 20"
        >
          <path
            d="M10 .5a9.5 9.5 0 1 0 9.5 9.5A9.51 9.51 0 0 0 10 .5ZM9.5 4a1.5 1.5 0 1 1 0 3 1.5 1.5 0 0 1 0-3ZM12 15H8a1 1 0 0 1 0-2h1v-3H8a1 1 0 0 1 0-2h2a1 1 0 0 1 1 1v4h1a1 1 0 0 1 0 2Z"
          />
        </svg>
        {{ isError }}
      </div>
    </div>
    <div class="w-[100%] flex flex-col gap-2 pb-5 pt-3">
      <label for="name" class="font-semibold text-[20px]">Nome: </label>
      <input
        type="text"
        name="name"
        class="form-control "
        maxlength="10"
        v-model="name"
      />
      <label for="name" class="font-semibold text-[20px]">Email: </label>
      <input type="email" class="form-control" v-model="email" />
      <div class="flex gap-3 my-2">
        <label for="numero" class="font-semibold text-[20px]">Telefone: </label>
        <input
          type="number"
          name="numero"
          class="form-control"
          v-model="telefone"
        />
        <label for="idade" class="font-semibold text-[20px]">Idade: </label>
        <input
          type="number"
          name="idade"
          class="form-control"
          v-model="idade"
        />
      </div>
      <label for="name" class="font-semibold text-[20px]">Descrição: </label>
      <input type="text" class="form-control" v-model="descricao" />
    </div>
    <div class="lg:flex lg:w-[100%]">
      <button class="btn btn-primary min-w-[50%]" @click="Cadastrar">
        Cadastrar
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Client-Form",
  data() {
    return {
      name: "Usuario",
      telefone: "",
      email: "",
      idade: "",
      descricao: "",
      isError: undefined,
    };
  },
  props: {
    CadastrarUsuario: Function,
  },
  methods: {
    Cadastrar: async function () {
      const result = await this.CadastrarUsuario({
        name: this.name,
        email: this.email,
        telefone: this.telefone,
        idade: this.idade,
        descricao: this.descricao,
        id: Date.now(),
      });
      if (result) return this.isError = result;
      this.name = "Usuario";
      this.telefone = "";
      this.email = "";
      this.idade = "";
      this.descricao = "";
    },
  },
};
</script>