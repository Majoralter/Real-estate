<script>
    import Showreel from "../../assets/pexels-david-mcbee-4770380-1920x1080-30fps (1) (1).mp4"
    import Icon from "../../assets/Frame 56084.svg"

       let x,y

    document.addEventListener("mousemove", e => {
        x =  e.clientX;
        y =  e.clientY;
    })
</script>

<section>
    <h2>
        Aesthetic.
    </h2>

    <p style="text-align: center;">
        We offer the most beautiful <br> homes and apartments available <br> for rent and sales
    </p>

    <div class="showreel_container">
        <video src="{Showreel}" autoplay muted loop width="100%" height="500px"></video>

        <div id="custom_cursor" style="left: {x}px; top: {y}px;">SHWRL</div>
    </div>

    <div class="showreel_footer">
        <img src="{Icon}" alt="">

        <h3 style="font-size: 2rem; color: #d6ba73">
            Indulge in the ultimate luxury with our <br> handcrafted furniture pieces. Impeccable <br> quality, exquisite design, and premium <br> materials are the hallmarks of our <br> collections. Browse our curated <br> selection and experience the opulence of <br> high-end furniture.
        </h3>
    </div>
</section>

<style lang="scss">
    section{
        height: fit-content;
        @include flex(column, center, center, 1.5rem);
        text-transform: uppercase;
        position: relative;

        h2{
            font-size: 15vw;
            line-height: 13vw;
        }

        .showreel_container{
            cursor: none;
            &:hover{
                #custom_cursor{
                    visibility: visible;
                }
            }

            #custom_cursor{
            @include flex(column, center, center, 0);
            transition: all .1s ease;
            height: 100px;
            width: 100px;
            background-color: #0D0D0D;
            border-radius: 50%;
            z-index: 2;
            position: absolute;
            pointer-events: none;
            visibility: hidden;
        }
        }

        .showreel_footer{
            width: 100%;
            @include flex(row, flex-start, space-between, 0);
            padding: 2rem 4rem;
        }
    }
</style>