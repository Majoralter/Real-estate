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
        width: 100%;
        position: fixed;

        nav{
            @include flex(row, center, space-between, 0);
            padding: 2rem;

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
    }
</style>