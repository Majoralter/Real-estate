<script>

</script>

<header>
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
</header>

<style lang="scss">
    header{
        background-color: #0D0D0D;
        nav{
            @include flex(row, center, space-between, 0);
            padding: 2rem;

            a{
                text-decoration: none;
                text-transform: uppercase;
                font-size: 1rem;
                color: #ffffff;
            }

            ul{
                @include flex(row, center, center, 2rem);
                list-style-type: none;
            }

            .free_consult{
                padding: 0.4375rem 1.5rem;
                border-radius: 1.25rem;
                outline: solid 1.5px #ffff;
                position: relative;
                overflow: hidden;

                &::before{
                    content: "";
                    width: 200%;
                    height: 200%;
                    position: absolute;
                    top: 0;
                    left: 0;
                    scale: 0;
                    background-color: orangered;
                    @include transition;
                }

                &:hover::before{
                    scale: 1;
                }
            }
        }
    }
</style>