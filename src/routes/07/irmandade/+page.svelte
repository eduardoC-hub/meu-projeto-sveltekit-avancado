<script>
    let {form} = $props();
</script>
<form method="post">
    nome: <input name="nome" type="text" placeholder="nome do aprendiz"/> 
    <br>
    nascimento: <input name="nascimento" type="date"/> 
    <br>
    força: <input name="forca" type="number" min="1" max="10"/>
    <br>
    inteligência: <input name="inteligencia" type="number" min="1" max="10"/>
    <br>
    destreza: <input name="destreza" type="number" min="1" max="10"/> 
    <br>
    conhecimento de magia: <input name="magia" type="checkbox"/>
    <br>
    ferramentas de artesao: <input name="ferramentas" type="checkbox"/> 
    <br> 
    <button formaction="?/guerreiros">inscrever na ordem dos guerreiros</button>
    <button formaction="?/magos">inscrever na circulo dos magos</button>
    <button formaction="?/artesaos">inscrever na guilda dos artesaos</button>
</form>
{#if form?.error}
<p style="color:red">{form.error}</p>
{/if}