<script>
import Titulo from '../_components/Titulo.svelte';
import {actualPage} from '../_components/stores'
let tams=['6','3.2']
</script>

<main>
    <img src="/imagenes/main/{$actualPage.main}.png" alt=""
    style="{$actualPage.imgStyle}">
    <div style="{$actualPage.divStyle?$actualPage.divStyle:''}">
        <Titulo {tams} {...$actualPage}></Titulo>
    </div>
</main>

<style>
main{
    min-height: 100vh;
}
div{
    width:60%;
    display:block
}
</style>