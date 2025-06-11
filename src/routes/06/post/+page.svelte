<script>
  let { form } = $props();
</script>

<main class="form-container">
  <form method="POST">
    <h2>Login</h2>

    <input name="email" type="email" placeholder="E-mail de usuário" value={form?.email || ''} required/>

    <input name="senha" type="password" placeholder="Senha"required/>

    <button type="submit">Entrar</button>

    {#if form?.error}
      <p class="error">{form.error}</p>
    {/if}
  </form>
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Inter', sans-serif;
    background-color: #f4f4f4;
  }

  .form-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    padding: 1rem;
  }

  form {
    background: white;
    padding: 2rem;
    border-radius: 1rem;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
    max-width: 400px;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  h2 {
    margin-bottom: 0.5rem;
    font-size: 1.75rem;
    text-align: center;
    color: #333;
  }

  input {
    padding: 0.75rem;
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    font-size: 1rem;
    transition: border 0.2s ease;
  }

  input:focus {
    border-color: #4f46e5;
    outline: none;
  }

  button {
    background-color: #4f46e5;
    color: white;
    padding: 0.75rem;
    border: none;
    border-radius: 0.5rem;
    font-size: 1rem;
    cursor: pointer;
    transition: background 0.2s ease;
  }

  button:hover {
    background-color: #4338ca;
  }

  .error {
    color: #e11d48;
    font-size: 0.9rem;
    text-align: center;
  }
</style>
