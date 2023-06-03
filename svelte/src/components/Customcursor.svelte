<script>
    let x,y

    document.addEventListener("mousemove", e => {
        x =  e.clientX;
        y =  e.clientY;
    })
</script>

<div id="custom_cursor" style="left: {x}px; top: {y}px;"></div>

<style lang="scss">
    #custom_cursor{
        height: 20px;
        width: 20px;
        background-color: #EC0B43;
        border-radius: 50%;
        z-index: -100;
        position: absolute;
        pointer-events: none;
        mix-blend-mode: difference;
    }
</style>