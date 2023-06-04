<script>
    let x,y

    document.addEventListener("mousemove", e => {
        x =  e.clientX;
        y =  e.clientY;
    })

    let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
        console.log(viewportWidth)
    })
</script>

{#if viewportWidth >= 1024}
<div id="custom_cursor" style="left: {x}px; top: {y}px;"></div>
{/if}

<style lang="scss">
    #custom_cursor{
        height: 20px;
        width: 20px;
        background-color: #EC0B43;
        border-radius: 50%;
        z-index: 2;
        position: absolute;
        pointer-events: none;
        mix-blend-mode: difference;
    }
</style>