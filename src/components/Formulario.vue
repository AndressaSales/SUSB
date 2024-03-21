<template>
    <div>
      <form id="form" @submit="finalizacao">
        <div class="container-inpu">
            <label for="nome">Nome do Paciente: </label>
            <input type="text" v-model="nome" name="nome" id="nome" placeholder="Digite seu nome.."> <br>
            <label for="cpf">Cpf: </label>
            <input type="text" v-model="cpf" name="cpf" id="cpf" placeholder="XXX.XXX.XXX.XX" > <br>
            <label for="email">E-mail:</label>
            <input type="text" v-model="email" id="email" placeholder="Maria@email.com">
        </div>
        <div class="container-inpu">
            <label for="especialidade">Especialidade:</label>
            <select name="especialidade" id="especialidade">
                <option value="">Selecione a especialidade</option>
                <option v-for="especialidade in especialidades" :key="especialidade.id" :value="especialidade.area">{{ especialidade.area }}</option>
            </select>
        </div>
        <div class="container-med">
           <select name="medicos" id="medicos">
            <option value="">Selecione o médico</option>
            <option v-for="medico in medicos" :key="medico.id" :value="medico.nome">{{ medico.nome }}</option>
           </select>
           <select name="horario" id="horario">
            <option value="">Horário</option>
            <option v-for="horario in horarios" :key="horario.id" :value="horario.h">{{ horario.h }}</option>
           </select>
        </div>
        <div>
            <input class="btn" type="submit" value="Finalizar marcação">
        </div>
      </form>
    </div>
</template>

<script>
export default{
    name: 'Formulario',
    data(){
        return{
            medicos: null,
            horarios: null,
            especialidades: null,
            nome: null,
            cpf: null,
            email: null,
            especialidade: null,
            medico: null,
            horario: null
        }
    },
    methods:{
        async getProfissoes(){
            const response = await fetch("http://localhost:3000/profissoes")
            const data = await response.json()
            //console.log(data)

           this.especialidades = data.especialidades
           this.medicos = data.medicos
           this.horarios = data.horarios
        },

        async finalizacao(e){
            e.preventDefault();

            const data = {
                nome: this.nome,
                cpf: this.cpf,
                email: this.email,
                especialidade: this.especialidade,
                medico: this.medico,
                horario: this.horario
            }

            console.log(data)

            this.nome = ""
            this.cpf = ""
            this.email = ""
            this.especialidade = ""
            this.medico = ""
            this.horario = ""
        }
    },
    mounted(){
        this.getProfissoes();
    }
}
</script>

<style scoped>
    #form{
        margin: 0 auto;
        max-width: 400px;
    }
    .container-inpu{
        display: flex;
        flex-direction: column;
        margin-bottom: 18px;
    }
    .container-inpu label{
        margin-bottom: 15px ;
        border-left: 5px solid #006414;
        font-weight: bold;
        padding: 5px 10px;
        color: #494949;
    }
    .container-inpu input{
        padding: 5px 10px;
        background: transparent;
        border-right: none;
        border-left: none;
        border-top: none;
        border-bottom: 2px solid #006414;
        font-size: 15px;
        width: 300px;
        outline: none;
    }
    .container-inpu select{
        padding: 5px 10px;
        border-right:none ;
        border-left:none ;
        border-top:none ;
        border-bottom: 2px solid #006414;
        font-size: 15px;
        outline: none;
        width: 300px;
    }
    .container-med select{
        border-right: none;
        border-left: none;
        border-top: none;
        border-bottom: 2px solid #006414;
        margin-bottom: 10px;
        font-size: 15px;
    }
    #horario{
        margin-left: 10px;
    }
    .container-med option{
        text-align: center;
        font-weight: bold;
    }
    .btn{
        width: 300px;
        padding: 12px;
        background-color: cornflowerblue;
        outline: none;
        border: none;
        font-weight: bold;
        cursor: pointer;
    }
</style>