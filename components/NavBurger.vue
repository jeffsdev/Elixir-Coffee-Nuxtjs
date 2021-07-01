<template>
    <div class="nav-burger" :class="{ 'nav-toggled': open }">
        <span :class="{ 'rotate-top': open }"></span>
        <span :class="{ 'transparent': open }"></span>
        <span :class="{ 'rotate-bottom': open }"></span>
    </div>
</template>

<script>
export default {
    props: ['open'],
}
</script>

<style lang="scss">
// nav burger and it's animations
.nav-burger {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 3.5em;
    margin-right: .5em;
    height: 100%;
    cursor: pointer;
    -webkit-tap-highlight-color: rgba(0,0,0,0);
    transition: all 0.3s ease-in-out;
    &.nav-toggled {
        margin-right: 0;
    }
    span {
        position: absolute;
        display: block;
        background: $coffee-light;
        height: .125em;
        width: 65%;
        transition: all 0.3s ease-in-out;
        &:nth-child(1) {
            top: 27%;
        }
        &:nth-child(2) {
            top: 50%;
        }
        &:nth-child(3) {
            top: 72%;
        }            
        &.transparent {
            opacity: 0;
        }
        &.rotate-top {
            transform:rotatez(45deg);
            transform-origin:0%;
            left: .5em; 
            transition:all 0.3s ease-in-out;
        }
        &.rotate-bottom {
            transform:rotatez(-45deg);
            transform-origin: 0%;
            left: .5em; 
            margin-top: .125em; 
            transition:all 0.3s ease-in-out;
        }    
    }
    @media screen and #{$sm-tablet} {
        display: none;
    }
}
</style>
