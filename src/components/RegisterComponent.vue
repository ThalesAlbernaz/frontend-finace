<template>
    <div>

        
        <form id="register-form" >

            <div class="input-container">
                <label for="nome">Nome</label>
                <input type="text" id="name" name="name" v-model="name" placeholder="Digite seu nome">
            </div>

            <div class="input-container">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" v-model="email" placeholder="Digite seu email">
            </div>

            <div class="input-container">
                <label for="senha">Senha</label>
                <input type="password" id="password" name="password" v-model="password" placeholder="Digite sua senha">
            </div>

            <div class="input-container">
                <input @click="submit" class="submit-btn" value="Entrar">
            </div>
        </form>
    </div>
</template>

<script>
import router from '@/router/index'
 import api from '@/services/api'  
    export default {
        data() {
            return {
                name: '' ,
                email: '',
                password:''
            }
        },

        methods: {
            submit() {
                var data = {
                    name: this.name ,
                    email: this.email,
                    password:this.password
                    
                }
               api.post('auth/register', data).then(function(response) { 
                response.data.data.user.id;
                alert('funfou')
                router.push('login')
            
            }).catch(function (error) {
                    console.log(error);
                }) ;
                
                
                // console.log(user)
    }
            
            
        }
    }
</script>

<style scoped>
    #register-form {
        font-family:  Avenir, Helvetica, Arial, sans-serif;
        max-width: 400px;
        margin: 0 auto;
    }
    .input-container {
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }

    label {
        font-weight: bold;
        margin-bottom: 15px;
        color: #222;
        padding: 5px 10px;
        border-left: 4px solid #B2ACFA;
    }

    input {
        padding: 5px 10px;
        width: 300px;
    }

    .submit-btn {
        background-color: #B2ACFA;
        font-weight: bold;
        border: 2px solid #B2ACFA;
        margin: 0 auto;
        cursor: pointer;
        transition: 0.5s;
    }

    .submit-btn:hover {
        background-color: transparent;
        color: #B2ACFA;
    }
</style>