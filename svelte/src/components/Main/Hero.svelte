<script>
    // @ts-ignore
    import gsap from 'gsap'
    import ScrollTrigger from 'gsap/ScrollTrigger'
    import { onMount } from 'svelte';

   

    onMount(() =>{
        gsap.registerPlugin(ScrollTrigger)

        gsap.from(".splt", {
        y: 30,
        opacity: 0,
        duration: 2
    })

        gsap.to(".splt", {
            scrollTrigger: {
                trigger: ".splt",
                scrub: true,
                start: "top 30%",
                end: "bottom top"
            },

            y: -50,
            ease: "ease",
        })
    })

    let viewportWidth = window.innerWidth

    window.addEventListener("resize", () =>{
        viewportWidth = window.innerWidth
        console.log(viewportWidth)
    })


    import circularText from "../../assets/best_customer_experience.svg"
    import heroimageOne from "../../assets/pexels-evg-kowalievska-1148955.jpg"
    import heroimageTwo from "../../assets/pexels-pixabay-276534.jpg"
</script>

{#if viewportWidth >= 768}
<main>
    <h1 class="top_heading splt">
        We <span><img src="{heroimageOne}" alt="A chair" class="img"></span> Only
    </h1>

    <div class="mid_text-container">
        <h1 class="mid_heading splt">
            offer
        </h1>

        <div class="overlay">
            <img src="{heroimageTwo}" alt="A chair" class="img">
        </div>

        <p>
            Welcome to our exclusive furniture website, <br> designed with the top 1% in mind. Discover <br>
            unparalleled quality and luxurious designs <br> that will transform your home into a <br> sanctuary of sophistication and elegance.
        </p>
    </div>

    <h1 class="bottom_text splt">
        comfort
    </h1>

    <img src="{circularText}" alt="" class="circular_text">
</main>

{:else if viewportWidth < 768}
<main>
    <p>
        hello world!
    </p>
</main>

{/if}

<style lang="scss">
    main{
        height: 100vh;
        @include flex(column, center, center, 0);
        position: relative;
        text-transform: uppercase;

        h1{
            font-size: clamp(3rem,10vw,10rem);
            font-weight: 400;
        }


        .top_heading{
            @include flex(row, center, center, 1rem);

            span{
                img{
                    height: 150px;
                    width: 250px;
                    object-fit: cover;
                }
            }
        }

        .circular_text{
            position: absolute;
            right: 19vw;
            top: 20vh;
            animation: rotate 5s linear infinite;
        }

        @keyframes rotate{
            0%{
                transform: rotate(0);
            }

            100%{
                transform: rotate(360deg);
            }
        }

        .mid_text-container{
            @include flex(row, flex-start, center, 1rem);

            .mid_heading{
                margin-top: -60px;
            }

           .overlay{
            display: inline-block;
            background-image: linear-gradient(to bottom, rgb(221, 167, 123, .2), rgba(45, 45, 42, .5));

             img{
                display: block;
                position: relative;
                z-index: -1;
                width: 200px;
                height: 300px;
                object-fit: cover;
            }
           }     
        }

        .bottom_text{
            position: absolute;
            bottom: 5rem;
        }

    }
</style>