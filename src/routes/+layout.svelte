<script>
import {page} from '$app/stores'
import { goto } from '$app/navigation'
</script>
{#if $page.url.pathname!=='/'}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <img src="/imagenes/home.png" alt="" on:click={()=>goto('/')}>
{/if}
<slot></slot>
<style>
    img{
        width:3em;
        position:fixed;
        top:0;
        left: 0;
        opacity:.5;
        cursor:pointer;
    }
</style>