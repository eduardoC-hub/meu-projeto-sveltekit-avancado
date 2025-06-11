<script>
    let name = "zeca urubu";
  </script>
  
  <main class="container">
    <h1>Bem-vindo(a), {name}!</h1>
    <p>É um prazer ter você aqui. Aproveite sua visita.</p>
  </main>
  
  <style>
    :global(body) {
      margin: 0;
      padding: 0;
      font-family: 'Inter', sans-serif;
      background-color: #f9f9f9;
      color: #333;
    }
  
    .container {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 2rem;
      text-align: center;
    }
  
    h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }
  
    p {
      font-size: 1.25rem;
      color: #555;
    }
  </style>
  