<main class="form-container">
  <form method="POST" action="/06/post">
    <h2>Envie seus dados</h2>

    <input type="number"name="umnumero"placeholder="Digite um número"required />

    <input name="umtexto"placeholder="Digite um texto"required/>

    <input name="umadata"type="date"required/>

    <button type="submit">Enviar</button>
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
    text-align: center;
    margin-bottom: 1rem;
    color: #333;
    font-size: 1.5rem;
  }

  input {
    padding: 0.75rem;
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    font-size: 1rem;
    transition: border-color 0.2s ease;
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
</style>
