<template>
    <main class="page-content-container about-page-content">
        <div class="hero-container">
            <h1>About Us</h1>
        </div>
        <section class="page-section">
            <div class="section-inner">
                <div class="logo">
                    <img src="~/assets/images/elixir-logo.svg" alt="elixir coffee">
                    <h2>Elixir Coffee</h2>
                </div>
            </div>
            <div class="about-icon-row">
                <div class="about-icon">
                    <img src="~/assets/images/planet-earth.svg" alt="Sustainably Sourced">
                    <span>Sustainably Sourced</span>
                </div>
                <div class="about-icon">
                    <img src="~/assets/images/coffee.svg" alt="Premium Coffee">
                    <span>Premium Coffee</span>
                </div>
                <div class="about-icon">
                    <img src="~/assets/images/coffee-beans.svg" alt="In-house Roasted">
                    <span>In-house Roasted</span>
                </div>                                       
            </div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere. Lorem ipsum dolor sit amet consectetur adipisicing elit. Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere.</p>            
        </section>       

        <section class="section-inner about-image-grid grid-3-col">
            <div class="about-image-grid__content">
                <h2>Lorem ipsum dolor sit amet</h2>
                <p>Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere.</p>
            </div>
            <img src="~/assets/images/sustainably-1.jpg" class="about-image-grid__image" alt="coffee cup">
            <img src="~/assets/images/coffeecup-1.jpg" class="about-image-grid__image" alt="barista">
            <div class="about-image-grid__content">
                <h2>Lorem ipsum dolor sit amet</h2>
                <p>Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere.</p>
            </div>
            <img src="~/assets/images/roasting-1.jpg" class="about-image-grid__image" alt="coffee bags">                           
            <div class="about-image-grid__content">
                <h2>Lorem ipsum dolor sit amet</h2>
                <p>Sit quidem asperiores ab ducimus aut maiores, eveniet nemo itaque sequi corrupti modi consequatur quibusdam quae doloribus labore sapiente temporibus! Voluptate, facere.</p>
            </div>
        </section> 
    </main>
</template>

<style lang="scss" scoped>
    .hero-container {
        background: url('~/assets/images/about-hero.jpg') center 80%/cover no-repeat;
    }
    
    .logo {
        display: flex;
        margin: auto;
        justify-content: center;
        align-items: center;
        img {
            max-height: 3em;
            margin-right: 10px;
        }
        h2 {
            padding-top: .5em;
            color: $coffee-dark;
            font-weight: 400;
            margin: 0;
        }
    }   

</style>