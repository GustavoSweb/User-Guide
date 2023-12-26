<template>
  <div class="flex flex-col p-3 shadow-xl my-[3em] rounded-lg max-w-[550px]">
    <div id="Header-Card" class="flex justify-betweem items-center">
      <div class="max-w-[100%] w-[400px] justify-center flex flex-col ">
       <div class="flex text-[#00000080]">
          <p class="block mb-0 ">Idade:</p><input type="number" :readonly="!isForm" v-model="idade" class="outline-none max-w-[130px] ml-1">
          
       </div>
        <div class="flex items-center mb-2"><h3 class="mb-0">Cliente:</h3><input type="text" :readonly="!isForm" v-model="name" class="outline-none max-w-[100%] block text-2xl text-bold mt-[0.09em] ml-2" id="inputName"></div>
      </div>
      <div>
        <button :class="['btn','max-w-[100%]',{'btn-primary': !isForm, 'btn-danger': isForm}]" @click="EditCard">{{isForm ? 'Salvar' : 'Editar'}}</button>
      </div>
    </div>
    <hr />
    <input type="text" :readonly="!isForm" v-model="descricao" class="outline-none max-w-[100%]">
    <hr />
    <div class="flex justify-between text-[#00000080]">
      <div >
        <small
          >Tel: </small
        > <input type="number" :readonly="!isForm" v-model="numero" class="outline-none max-w-[130px] ml-1">
      </div>
      <div class=" flex items-center">
        <small
          >Email: </small
        > <input type="email" :readonly="!isForm" v-model="email" class="outline-none min-w-[250px] ml-1">
      </div>
    </div>
  </div>
</template>
<script>

export default {
  name: "Client-Card",
  data(){
    return{
      name:this.data.name,
      descricao: this.data.descricao,
      numero: this.data.numero,
      email: this.data.email,
      idade: this.data.idade,
      isForm: false,
    }
  },
  props: {
   data:Object,
  },
  methods:{
    EditCard: function(){
      let select = !this.isForm
      this.isForm = select
      
    }
  }
};
</script>
