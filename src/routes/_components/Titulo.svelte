<script>
export let titulo;
export let sub;
export let tams=[];
</script>

<h1 style="font-size: {tams[0]}em;">{titulo}</h1>
<h2 style="font-size: {tams[1]}em;">{sub}</h2>

<style>
h1,h2{
    background:rgba(255, 255, 255, 0.922);
    color: var(--green)
}
h1{

    margin-bottom: 0;
}
h2{
    margin-top: 0;

}
</style>