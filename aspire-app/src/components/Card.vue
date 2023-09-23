<template>
    <PrimeCard>
        <template #content>
            <section class="card-body">
                <div class="issuer-logo">
                    <img :src="aspireLogo" alt="Aspire">
                </div>
                <div class="card-holder-name">
                    {{ cardHolderName }}
                </div>
                <div class="card-number">
                    <p class="card-dot">.... .... ....</p>
                    <p class="card-last-four">2020</p>
                </div>
                <div class="thru">Thru: 12/20</div>
                <div class="cvv">
                    <p class="cvv-label">CVV:</p>
                    <p class="cvv-value">***</p>
                </div>
                <div class="card-scheme">
                    <img :src="visaLogo" alt="VISA">
                </div>
            </section>
        </template>
    </PrimeCard>
</template>
<script lang="ts">
import { Component, Vue, toNative, Prop } from 'vue-facing-decorator';
import PrimeCard from 'primevue/card';
import aspireLogo from '@/assets/icons/aspire_logo.png';
import visaLogo from '@/assets/icons/visa_logo.png';

@Component({
    components: {PrimeCard}
})
class Card extends Vue {
    @Prop({
        type: String,
        default: 'Mark Henry'
    }) cardHolderName!: string;

    @Prop({
        type: String,
        default: '#01D167'
    }) cardColor!: string;

    aspireLogo = aspireLogo;
    visaLogo = visaLogo;

}
export default toNative(Card);
</script>

<style scoped lang="scss">
.p-card {
    background-color: v-bind('cardColor');
    border-radius: 12px;
    height: 220px;
    width:358px;
}

.card-body {
    display: grid;
    grid-template-columns: repeat(20, 1fr);
    grid-template-rows: repeat(4, 1fr);
}

.issuer-logo {
    grid-row: 1;
    grid-column: 16 / span 2;
    max-width: 74px;
    max-height: 21px;
    padding-top: 20px;
}

.card-holder-name {
    margin-top: 18px;
    font-family: 'Open Sans';
    color: white;
    font-size: 22px;
    grid-row: 2;
    grid-column: 2 / span 18;
    font-weight: bold;
}

.card-number {
    position: relative;
    font-family: 'Open Sans';
    color: white;
    font-size: 22px;
    grid-row: 3;
    grid-column: 2 / span 18;
    .card-dot {
        position: absolute;
        top: -20px;
        color: white;
        font-weight: bold;
        font-size: 50px;
    }
    .card-last-four {
        position: absolute;
        left: 210px;
        top: 25px;
        font-size: 14px;
        font-weight: bold;
    }
}

.thru {
    font-family: 'Open Sans';
    grid-row: 4;
    grid-column: 2 / span 4;
    color: white;
    font-size: 13px;
    font-weight: 600;
}

.cvv {
    grid-row: 4;
    grid-column: 8 / span 3;
    color: white;
    font-family: 'Open Sans';
    display: flex;
    .cvv-label {
        font-family: 'Open Sans';
        font-size: 13px;
        font-weight: bold;
    }
    .cvv-value {
        position: absolute;
        top: 260px;
        left: 180px;
        color: white;
        font-weight: bold;
        font-size: 24px;
    }
}
.card-scheme {
    grid-row: 4;
    grid-column: 17 / span 2;
    max-width: 59px;
    max-height: 20px;
    margin-top: 20px;
}
</style>