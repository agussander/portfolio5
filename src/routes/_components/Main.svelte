<script>
function randomIntFromInterval(min, max) { // min and max included 
    return Math.floor(Math.random() * (max - min + 1) + min)
}

const nombre=[
    {l:'A', c:1},
    {l: 'g', c:1},
    {l:'u',c:1},
    {l:'s',c:1}
];
const apellido=[
    {l:'S',c:1},
    {l:'a',c:1},
    {l:'n',c:1},
    {l:'d',c:1},
    {l:'e',c:1},
    {l:'r',c:1},
];

const change=(target,i)=>{
    const newClass = randomIntFromInterval(1, 12);
    target=='apellido' ? apellido[i].c=newClass : nombre[i].c=newClass;
}

let ticking=false;
let intervall;

const handleMouse=(target,i)=>{
    /*
    if(ticking==false){
        ticking=true;
        change(target,i)
        setTimeout(()=>{ticking=false},300);
        console.log(i)
    }
    ticking=true;
    */
    change(target,i)
    if(!intervall){
        intervall= setInterval(()=>{console.log('s');change(target,i)},200);
    }
}

</script>

<div style="margin-top:-4em">
    {#each nombre as {l,c},i}
        <!-- svelte-ignore a11y-mouse-events-have-key-events -->
        <p
        on:mouseenter={()=>handleMouse('nombre',i)}
        on:mouseleave={()=>{clearInterval(intervall);intervall=null;}}
        class="p-{c}"
        >{l}</p>
    {/each}
</div>
<div style="margin-top: -6em">
    {#each apellido as {l,c},i}
        <!-- svelte-ignore a11y-mouse-events-have-key-events -->
            <p
            on:mouseenter={()=>handleMouse('apellido',i)}
            on:mouseleave={()=>{clearInterval(intervall);intervall=null;}}
            class="p-{c} up"
            >{l}</p>
    {/each}
</div>
<p class="sub">diseño · desarrollo · arte</p>

<style>

p{
    display: inline;
    font-size: 16em;
    cursor: default;
    color:var(--green);
    transition: all ease 300ms;

}
.sub{
    font-family: 'Helvetica';
    color:gray;
    font-size: 1.2em;
    font-weight: 200;
    padding-left: 1em;
    display: block;
    position:absolute;
    top:20em
}


.p-1{
    font-family: swear-display, serif;
    font-weight: 800;
    font-style: normal;
}
.p-2{
    font-family: bd-supper, sans-serif;
    font-weight: 700;
    font-style: normal;
}
.p-3{
    font-family: lust-script-fine, sans-serif;
    font-weight: 100;
    font-style: normal;
}
.p-4{
    font-family: marshmallow-script, sans-serif;
    font-weight: 400;
    font-style: normal;
}
.p-5{
    font-family: miller-banner, serif;
    font-weight: 700;
    font-style: italic;
}
.p-6{
    font-family: input-serif, serif;
    font-weight: 100;
    font-style: normal;
}
.p-7{
    font-family: los-feliz, serif;
    font-weight: 400;
    font-style: italic;
}
.p-8{
    font-family: fatfrank, sans-serif;
    font-weight: 400;
    font-style: normal;
}
.p-9{
    font-family: ratiomodern, serif;
    font-weight: 800;
    font-style: normal;
}
.p-10{
    font-family: lust-script-display, sans-serif;
    font-weight: 400;
    font-style: normal;
}
.p-11{
    font-family: brix-slab, serif;
    font-weight: 400;
    font-style: normal;
}
.p-12{
    font-family: ff-chambers-sans-web, sans-serif;
    font-weight: 700;
    font-style: normal;
}
</style>

