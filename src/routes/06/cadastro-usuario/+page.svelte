<script>
    let nome = '';
    let email = '';
    let dataNascimento = '';
    let erros = {
      nome: '',
      email: '',
      dataNascimento: ''
    };
  
    const validarFormulario = () => {
      erros = { nome: '', email: '', dataNascimento: '' };
      let valido = true;
  
      // Validação do nome
      if (nome.trim().length < 2) {
        erros.nome = 'O nome deve ter pelo menos 2 caracteres.';
        valido = false;
      }
  
      
      const emailRegex = /^[a-zA-Z]+@[a-zA-Z]+\.[a-zA-Z]+$/;
      const partesEmail = email.trim().split('@');
      if (
        !emailRegex.test(email) ||
        partesEmail.length !== 2 ||
        partesEmail[1].split('.').length < 2
      ) {
        erros.email = 'Email inválido. Use o formato: letras@dominio.extensao';
        valido = false;
      }
  
      const nascimento = new Date(dataNascimento);
      const hoje = new Date();
      let idade = hoje.getFullYear() - nascimento.getFullYear();
      const mes = hoje.getMonth() - nascimento.getMonth();
      const dia = hoje.getDate() - nascimento.getDate();
      if (mes < 0 || (mes === 0 && dia < 0)) idade--;
  
      if (!dataNascimento || isNaN(nascimento) || idade < 12) {
        erros.dataNascimento = 'É necessário ter no mínimo 12 anos.';
        valido = false;
      }
  
      return valido;
    };
  
    const enviarFormulario = (e) => {
      e.preventDefault();
      if (validarFormulario()) {
        console.log({ nome, email, dataNascimento });
        alert('Cadastro realizado com sucesso!');
      }
    };
  </script>
  
  <style>
    form {
      max-width: 400px;
      margin: auto;
      font-family: Arial, sans-serif;
    }
    label {
      font-weight: bold;
      margin-top: 10px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-top: 4px;
      box-sizing: border-box;
    }
    .erro {
      color: red;
      font-size: 0.9em;
    }
  </style>
  
  <form onsubmit={enviarFormulario}>
    <label for="nome">Nome:</label>
    <input id="nome" bind:value={nome} required />
    {#if erros.nome}
      <div class="erro">{erros.nome}</div>
    {/if}
  
    <label for="email">Email:</label>
    <input id="email" type="email" bind:value={email} required />
    {#if erros.email}
      <div class="erro">{erros.email}</div>
    {/if}
  
    <label for="dataNascimento">Data de Nascimento:</label>
    <input id="dataNascimento" type="date" bind:value={dataNascimento} required />
    {#if erros.dataNascimento}
      <div class="erro">{erros.dataNascimento}</div>
    {/if}
  
    <button type="submit" style="margin-top: 15px;">Cadastrar</button>
  </form>
  