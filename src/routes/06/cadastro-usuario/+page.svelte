<script>
  let {data} = $props()
</script>

<form method="POST">
<input name = "nome" placeholder="nome de usuario" value={form?.nome || ''} required/>
<input name = "email" type="email" placeholder="email" value={form?.email || ''} required/>
<input name = "senha" type="password" placeholder="senha"value={form?.senha || ''} required/>
<input name ="confirmarsenha" type="password" placeholder="confirmar senha" value={form?.confirmarsenha || ''} required/>
<input name="nascimento" type="date" value={form?.nascimento || ''} required/>
<button type="submit">Cadastrar</button>
</form>

{#if form?.erros.length > 0}
{#each form.erros as error}
  <p style="color: red">{error}</p>
{/each}
{/if}


