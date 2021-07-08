<template>
    <main class="page-content-container about-page-content">
        <div class="hero-container">
            <h1>Menu</h1>
        </div>
        <section class="page-section">
            <div class="section-inner menu-intro">
                <div class="menu-intro">
                    <h2>Our Coffee</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima quod dolore ea veniam laudantium ratione doloribus facere, dolor ullam iusto maxime totam neque, nisi magni? <br>Reprehenderit perspiciatis vero harum animi.</p>
                </div>
                <div class="menu-items">
                    <div v-for="(item, key) in menuDrinks" :key="key" class="menu-items__item">
                        <div>
                            <span class="menu-items__name">{{item.name}}</span>
                            <span class="menu-items__price">${{item.price}}</span>
                        </div>
                        <span class="menu-items__description">{{item.description}}</span>
                    </div>                
                </div>
                <div class="menu-intro">
                    <h2>Bites</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima quod dolore ea veniam laudantium ratione doloribus facere, dolor ullam iusto maxime totam neque, nisi magni? <br>Reprehenderit perspiciatis vero harum animi.</p>
                </div>                
                <div class="menu-items">
                    <div v-for="(item, key) in menuBites" :key="key" class="menu-items__item">
                        <div>
                            <span class="menu-items__name">{{item.name}}</span>
                            <span class="menu-items__price">${{item.price}}</span>
                        </div>
                        <span class="menu-items__description">{{item.description}}</span>
                    </div>                
                </div>                
            </div>
        </section>     
    </main>
</template>

<script>
import data from '~/static/data.json';

export default {
    data() {
        return {
            menuDrinks: data.drinks,
            menuBites: data.bites,
        }
    }
}
</script>


<style lang="scss">
    .menu-intro {
        text-align: center;
    }

    .menu-items {
        display: grid;
        grid-gap: 2em 4em;
        margin: 4em auto;
        @media screen and #{$tablet} {
            grid-template-columns: 1fr 1fr;
        }
        &__name {
            order: 0;
            font-size: 1.25em;
            font-weight: 700;
            flex-shrink: 0;
        }
        &__price {
            flex-shrink: 0;
            order: 3;
        }
        &__description {
            font-style: italic;
        }
    }

    .menu-items__item {
        text-align: left;
        & > div {
            display: flex;
            justify-content: space-between;
            align-items: flex-end;
            line-height: 1;
            margin-bottom: .5em;
        }
        & > div::after {
            order: 1;
            content: "";
            display: inline-block;
            width: 100%;
            height: 1px;
            margin: 0 1em;
            background: rgba(0,0,0,0.25);
        }        
    }

</style>