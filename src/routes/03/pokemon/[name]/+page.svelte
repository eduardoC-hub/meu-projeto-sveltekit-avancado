
<script>
    let { data } = $props();
  </script>
  
  <div class="card mx-auto" style="max-width: 600px;">
    <img src={data.pokemon.image} alt={data.pokemon.name} class="card-img-top p-3" />
  
    <div class="card-body">
      <h2 class="card-title text-capitalize">{data.pokemon.name} (#{data.pokemon.id})</h2>
  
      <p><strong>Altura:</strong> {data.pokemon.height /10} m</p>
      <p><strong>Peso:</strong> {data.pokemon.weight /10} kg</p>
  
      <p><strong>Tipos:</strong>
        {#each data.pokemon.types as type, i}
          <span class="badge text-bg-primary me-1 text-capitalize">{type}</span>
        {/each}
      </p>
  
      <p><strong>Habilidades:</strong>
        {#each data.pokemon.abilities as ability, i}
          <span class="badge text-bg-success me-1 text-capitalize">{ability}</span>
        {/each}
      </p>
  
      <h5 class="mt-4">Status Base</h5>
      <ul class="list-group">
        {#each data.pokemon.stats as stat}
          <li class="list-group-item d-flex justify-content-between align-items-center">
            <span class="text-capitalize">{stat.name}</span>
            <span class="badge text-bg-secondary">{stat.value}</span>
          </li>
        {/each}
      </ul>
  
      <a href="/03/pokemon" class="btn btn-secondary mt-4">← Voltar</a>
    </div>
  </div>
  