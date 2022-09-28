<template>
    <div>
        <form id="register-form">

            <div class="input-container">
                <label for="nome">Nome</label>
                <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite seu nome">
            </div>

            <div class="input-container">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" v-model="email" placeholder="Digite seu email">
            </div>

            <div class="input-container">
                <label for="senha">Senha</label>
                <input type="password" id="senha" name="senha" v-model="senha" placeholder="Digite sua senha">
            </div>

            <div class="input-container">
                <input type="submit" class="submit-btn" value="Entrar">
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: "RegisterComponent"
    }
</script>

<style lang="scss" scoped>
    #register-form {
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