<script>
    import Main2 from "./_components/Main2.svelte";
    import Menu from "./_components/Menu.svelte";

</script>

<main>
    <Main2></Main2>
</main>
<section>
    <Menu></Menu>
</section>


<style>
main{
    min-height: 110vh;
    position:fixed;
    z-index:10;
}
section{
    position:absolute;
    top:100vh;
    z-index: 20;
    background: white;
}
</style>