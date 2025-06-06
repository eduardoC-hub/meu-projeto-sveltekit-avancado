<script>
let {data} = $props();
</script>

<h1>Lista de Usuários</h1>
<form>
    <input name="genero" type="text" placeholder="digite algum genero"/>
    
    <button>Filtrar</button>
</form>
<ul>
    {#each data.users.users as user}
        <li>
            <a href="/03/dummy/users/{user.id}">
                {user.firstName} {user.lastName} ({user.username}) {user.age} anos
            </a>
        </li>
    {/each}
</ul>
