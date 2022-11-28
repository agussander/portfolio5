<script>
function randomIntFromInterval(min, max) { // min and max included 
    return Math.floor(Math.random() * (max - min + 1) + min)
}
let defaultC=4;
const nombre=[
    {l:'A', c:defaultC},
    {l: 'g', c:defaultC},
    {l:'u',c:defaultC},
    {l:'s',c:defaultC}
];
const apellido=[
    {l:'S',c:defaultC},
    {l:'a',c:defaultC},
    {l:'n',c:defaultC},
    {l:'d',c:defaultC},
    {l:'e',c:defaultC},
    {l:'r',c:defaultC},
];

const change=(target,i)=>{
    const newClass = randomIntFromInterval(1, 6);
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

<div class="word">
    {#each nombre as {l,c},i}
        <!-- svelte-ignore a11y-mouse-events-have-key-events -->
        <div class=letter>
            <p class="p-{c}">{l}</p>
            <div class="hitbox"
            on:mouseenter={()=>handleMouse('nombre',i)}
            on:mouseleave={()=>{clearInterval(intervall);intervall=null;}}
            ></div>
        </div>
    {/each}
</div>
<div  class="word" style="transform:translateY(-60px)">
    {#each apellido as {l,c},i}
        <div class="letter">
        <!-- svelte-ignore a11y-mouse-events-have-key-events -->
            <p
            class="p-{c}">{l}</p>
            <div class="hitbox"
            on:mouseenter={()=>handleMouse('apellido',i)}
            on:mouseleave={()=>{clearInterval(intervall);intervall=null;}}
            ></div>
        </div>
    {/each}
</div>
<span class="sub">diseño · desarrollo · arte</span>

<style>
.word{
    display:flex;
}
.letter{
    display:block;
    position: relative;

}
.hitbox{
    width:100%;
    height:10em;

    position: absolute;
    top:30%;
    z-index: 40;
}
p{
    display: inline;
    font-size: 16em;
    cursor: default;
    color:var(--green);
    transition: all ease 300ms;
    line-height: 1em;
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
    font-weight: 300;
    font-style: normal;
}
.p-2{
    font-family: swear-display, serif;
    font-weight: 400;
    font-style: normal;
}
.p-3{
    font-family: swear-display, serif;
    font-weight: 500;
    font-style: normal;
}
.p-4{
    font-family: swear-display, serif;
    font-weight: 600;
    font-style: normal;
}
.p-5{
    font-family: swear-display, serif;
    font-weight: 700;
    font-style: italic;
}
.p-6{
    font-family: swear-display, serif;
    font-weight: 800;
    font-style: normal;
}
</style>

