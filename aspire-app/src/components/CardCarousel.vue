<template>
    <Carousel
        :value="products"
        :numVisible="1"
        :numScroll="3"
        :showNavigators="false"
        :showIndicators="true"
        :responsiveOptions="responsiveOptions"
    >
        <template #item="slotProps">
            <Card :card-holder-name="slotProps.data.cardHolderName" :card-color="slotProps.data.cardColor"></Card>
        </template>
    </Carousel>
</template>

<script lang="ts">
import { Component, Vue, toNative } from 'vue-facing-decorator';
import Carousel from 'primevue/carousel';
import Card from '@/components/Card.vue';
import {ref} from 'vue';

@Component({
    components: {Carousel, Card}
})
class CardCarousel extends Vue {
    products = ref([
        {cardHolderName: 'Naman Arora', cardColor: '#01D167'},
        {cardHolderName: 'Shubhi Arora', cardColor: '#536DFF'},
        {}
        // {src: new URL('../assets/img/sewage-system/02.jpeg', import.meta.url)},
        // {src: new URL('../assets/img/sewage-system/03.jpeg', import.meta.url)},
        // {src: new URL('../assets/img/sewage-system/04.jpeg', import.meta.url)},
        // {src: new URL('../assets/img/sewage-system/05.jpeg', import.meta.url)},
    ]);

    responsiveOptions = [{
        breakpoint: '1399px',
        numVisible: 3,
        numScroll: 3
    },
    {
        breakpoint: '1001px',
        numVisible: 2,
        numScroll: 2
    },
    {
        breakpoint: '414px',
        numVisible: 1,
        numScroll: 1
    }];
}
export default toNative(CardCarousel);
</script>

<style lang="scss">
.p-carousel-items-container {
    gap: 10px;
}

.p-carousel-indicators.p-reset {
    list-style: disc;
}
</style>