<template>
  <div class="main-container">
    <header>
      <section class="logo-container">
        <img :src="logo" alt="Aspire">
      </section>
      <section class="account-detail-wrapper">
        <div class="account-balance">Account balance</div>
        <div class="currency">
          <p class="currency-details">S$</p>
        </div>
        <div class="amount">3,000</div>
        <div class="new-card">
          <img class="new-card-logo" :src="addCard" alt="Add">
          <p class="new-card-label">New Card</p>
        </div>
      </section>
    </header>
    <section class="card-carousel">
      <CardCarousel></CardCarousel>
    </section>
    <section></section>
    <footer>
    </footer>
  </div>
</template>

<script lang="ts">
import { Component, Vue, toNative } from 'vue-facing-decorator';
import logo from "@/assets/icons/logo.svg";
import addCard from "@/assets/icons/add.svg";
import CardCarousel from '@/components/CardCarousel.vue';

@Component({
  components: { CardCarousel }
})
class App extends Vue {
  text = "";
  logo = logo;
  addCard = addCard;
}

export default toNative(App);
</script>

<style scoped lang="scss">
.main-container {
  padding: 20px 20px 0px 0px;
  background-color: #0C365A;
  min-height: 100vh;
  min-width: 100vw;
  .logo-container {
    display: flex;
    flex-direction: row-reverse;
  }

  .balance-header {
    padding-left: 15px;
  }
  .account-balance {
    font-size: 14pt;
    color: white;
    font-family: 'Open Sans', Semibold;
  }

  .account-detail-wrapper {
    padding-left: 20px;
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    grid-template-rows: 1fr 1fr;
    column-gap: 8px;
    row-gap: 2px;
  }

  .account-balance {
    font-family: 'Open Sans';
    font-weight: 500;
    font-size: 14px;
    grid-row: 1;
    grid-column: 1 / span 4;
  }

  .currency {
    grid-row: 2;
    grid-column: 1;
    background-color: #01D167;
    border-radius: 4px;
    width: 40px;
    height: 22px;
    .currency-details {
      font-weight: bold;
      text-align: center;
      vertical-align: center;
      color: white;
      font-size: 12px;
    }
  }
  .amount {
    grid-row: 2;
    grid-column: 2 / span 2;
    color: white;
    font-weight: 700;
    font-family: 'Open Sans';
    font-size: 22px;
    margin-top: -6px;
  }

  .new-card {
    display: flex;
    flex-direction: row;
    grid-row: 2;
    grid-column: 8 / span 3;
    margin-top: 3px;
    .new-card-logo {
      height: 16px;
      width: 16px;
    }
    .new-card-label {
      color: #23CEFD;
      font-family: 'Open Sans';
      font-weight: bold;
      font-size: 13px;
      margin-left: 5px;
      margin-top: -2px;
    }
  }

  .card-carousel {
    margin-left: 20px;
  }
}
</style>
