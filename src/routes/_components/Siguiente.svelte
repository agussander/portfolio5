<script>
import Titulo from "./Titulo.svelte";
import {works,actualPage} from './stores'
import {goto} from '$app/navigation'
let tams=['4','2'];
export let n;
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div on:click={()=>{goto($works[n].a); $actualPage=$works[n]}}>
    <p>Siguiente</p>
    <Titulo {tams} {...$works[n]}></Titulo>
</div>

<style>
p{
    font-family: 'avenir';
    margin-top: 4em;
    margin-bottom: -3em;
    color:gray
}
div{
    margin-left: 20vw;
    margin-bottom: 4em;
    background: url(/imagenes/flecha.png);
    background-size: contain;

    background-position: right;
    width:60vw;
    cursor:pointer;
}
</style>