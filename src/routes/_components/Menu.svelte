<script>
    import { goto } from "$app/navigation";
    import { works,actualPage } from "./stores";
    import Titulo from "./Titulo.svelte";

    let x;
    let y;
const handleMouse=(e)=>{
    x=e.clientX;
    y=e.clientY;
}
</script>

<div class="cont">
<div class="flex">
    {#each $works as {portada},i}
        <img src="/imagenes/portadas/{portada}.png" alt=""
        on:mousemove={handleMouse}
        on:mouseenter={()=>$actualPage=$works[i]}
        on:mouseleave={()=>$actualPage=null}
        on:click={()=>goto($actualPage.a)}
        >
    {/each}
</div>
</div>
{#if $actualPage}
    <div class="titulo" style="top:{y}px; left:{x}px;" >
        <Titulo tams={['4','2']} {...$actualPage}></Titulo>
    </div>
{/if}

<style>
    .titulo{
        position:fixed;
        pointer-events:none
    }
    .cont{
        max-width: 100vw;
    }
    .flex{
        display:flex;
        max-width:100vw;
        gap:0;
        flex-flow: row wrap
    }
    img{
        width:50%;
        cursor:pointer;
        margin-bottom: 0;
        object-fit: cover;
    }
    img:hover{
        opacity:.4
    }
  
</style>