<template>
    <main class="page-content-container about-page-content">
        <div class="hero-container">
            <h1>Locations</h1>
        </div>
        <section class="page-section">
            <div class="section-inner">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere. Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere.</p>
            </div>
        </section>
        <section class="page-section-full location-big location-big--burnside">
            <div class="location-big__heading location-big__heading--burnside">
                <h2>Burnside</h2>
            </div>
            <div class="location-big__content">
                <div class="location-big__content-inner">
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Atque doloremque deleniti facere, ut officiis fuga hic consequatur doloribus qui minus quia obcaecati itaque dolore quos dolor, inventore nostrum, rem iure?</p>
                </div>
                <img src="~/assets/images/location-bn.jpg" class="location-big--m-image" alt="Burnside">                
            </div>
        </section>
        <section class="page-section-full location-big location-big--mississippi">
            <div class="location-big__heading location-big__heading--mississippi">
                <h2>Mississippi</h2>
            </div>
            <div class="location-big__content">
                <div class="location-big__content-inner">
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Atque doloremque deleniti facere, ut officiis fuga hic consequatur doloribus qui minus quia obcaecati itaque dolore quos dolor, inventore nostrum, rem iure?</p>
                </div>
                <img src="~/assets/images/location-ms.jpg" class="location-big--m-image" alt="Mississippi">
            </div>
        </section>        
    </main>
</template>

<style lang="scss">
    .hero-container {
        background: url('~/assets/images/locations-hero.jpg') center 80%/cover no-repeat;
    }

    .location-big__heading {
        color: #fff;
        text-align: center;
        padding: 2em 1em;
        line-height: 1;
        h2 {
            margin-bottom: 0;
        }
    }

    .location-big__heading--burnside {
        background: $alt-blue;
    }
    .location-big__heading--mississippi {
        background: $coffee-light;
    }    

    .location-big--burnside {
        .location-big__content {
            @media screen and #{$desktop} {
                background: url('~/assets/images/location-bn.jpg') center/cover no-repeat fixed;
            }             
        }
    }
    .location-big--mississippi {
        .location-big__content {
            @media screen and #{$desktop} {
                background: url('~/assets/images/location-ms.jpg') center/cover no-repeat fixed;
            }             
        }
        .location-big__content-inner {
            margin-left: auto;   
        }
    }    
    .location-big__content {
        @media screen and #{$desktop} {
            min-height: 350px;
            height: 50vw;
            max-height: 90vh;
        }
        p {
            margin-bottom: 0;
        }
    }
    .location-big__content-inner {
        display: flex;
        align-items: center;
        justify-content: center;
        color: #fff;
        padding: 2em;
        background: rgba(0,0,0,1);
        @media screen and #{$desktop} {
            width: 50%;
            height: 100%;
            background: rgba(0,0,0,0.75);
        }         
    }       


    .location-big--m-image {
        width: 100%;
        object-fit: cover;
        object-position: center;
        max-height: 400px;
        @media screen and #{$desktop} {
            display: none;
        }   
    }

    @media screen and #{$desktop} {

    } 

</style>