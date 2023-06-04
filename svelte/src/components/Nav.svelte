<script>
     let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
        console.log(viewportWidth)
    })

    let isActive = false

    const handleClick = () =>{
        isActive = !isActive
        console.log("clicked")
    }
</script>

<header>
    {#if viewportWidth >= 700}
    <nav>
        <!-- svelte-ignore a11y-invalid-attribute -->
        <a href="#" class="logo">
            RealEstate
        </a>

        <ul>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li class="nav_links"><a href="#">Home</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li class="nav_links"><a href="#">For sale</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li class="nav_links"><a href="#">For rent</a></li>
            <!-- svelte-ignore a11y-invalid-attribute -->
            <li class="nav_links"><a href="#">About</a></li>
        </ul>

        <a href="#" class="free_consult">
            Free consult
        </a>
    </nav>
    
    {:else}

    <nav class="mobile_nav" class:active={isActive}>
        <div class="menu" on:click={handleClick}>
            <span class="menu_bar menu_item-one" class:active={isActive}></span>
            <span class="menu_bar menu_item-two" class:active={isActive}></span>
        </div>

        <ul class:active={isActive}>
            <hr>
            <li class="nav_links-mobile"><a href="#">Home</a></li>
            <li class="nav_links-mobile"><a href="#">For sale</a></li>
            <li class="nav_links-mobile"><a href="#">For rent</a></li>
            <li class="nav_links-mobile"><a href="#">About</a></li>
            <hr>
        </ul>
    </nav>
    {/if}
</header>

<style lang="scss">
    header{
        nav{
            @include flex(row, center, space-between, 0);
            padding: 2vw;

            a{
                text-decoration: none;
                font-size: 1rem;
                color: #ffffff;
                pointer-events: all;
                @include transition;

                &:hover{
                    filter: drop-shadow(0 0 1em #EC0B43);
                }
            }

            

            ul{
                @include flex(row, center, center, 2rem);
                list-style-type: none;
                text-transform: uppercase;
            }

            .free_consult{
                padding: 0.4375rem 1.5rem;
                border-radius: 1.25rem;
                outline: solid 1.5px #ffff;
                text-transform: uppercase;
            }
        }

        .mobile_nav{
            @include flex(column, center, center,0);
            height: 100vh;
            position: relative;
            background-color: #0d0d0d;
            @include transition;
            
            clip-path: circle(30px at 50% 6%);

            &.active{
                clip-path: circle(150% at 100% 100%);
                transition-delay: .3s;
            }

            .menu{
                position: absolute;
                height: 20px;
                width: 35px;
                top: 2rem;
                @include flex(column, center, center, .2rem);

                .menu_bar{
                    width: 90%;
                    height: 2px;
                    background-color: #fff;
                    @include transition;
                }

                .menu_item-one{
                    &.active{
                        width: 80%;
                        transform: rotate(-45deg) translate(-3px, 9px);
                        background-color: #EC0B43;
                    }
                }

                .menu_item-two{
                    &.active{
                        width: 80%;
                        transform: rotate(45deg) translate(4px, 0px);
                        background-color: #EC0B43
                    }
                }
            }

            ul{
                @include flex(column, center, space-between, 2rem);
                @include transition;
                transition-delay: .5s;

                opacity: 0;
                transform: translateY(50px);

                &.active{
                    opacity: 1;
                    transform: translateY(0);
                }

                a{
                    font-size: 5vw;
                    color: #D6BA73;
                }

                hr{
                    width: 200%;
                    border: solid 1px #D6BA73;
                }
            }
        }
    }
</style>