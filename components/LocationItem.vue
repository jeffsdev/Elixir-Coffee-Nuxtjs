<template>
    <div class="location-item">
        <h3>{{location.name}}</h3>
        <div>
            <img src="~/assets/images/icon-pin.svg" alt="address">
            <span class="address">{{location.address}}</span>
        </div>
        <div>
            <img src="~/assets/images/icon-clock.svg" alt="hours">
            <span class="hours">Open {{location.hours}}</span>
        </div>
        <div>
            <img src="~/assets/images/icon-phone.svg" alt="phone">
            <span class="phone">{{location.phone}}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: ['location']
}
</script>