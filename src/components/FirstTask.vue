<template>
  <div class="_container">
    <div class="main-page-wrapper">
      <div class="info-block">
        <h1 class="info-block__header">send<br>a request</h1>
        <div class="info-block__wrapper">
          <p class="info-block__description">
            leave your contacts<br>
            and we will contact<br>
            you as soon as possible
          </p>
          <a href="#" class="info-block__logo-link">
            <img src="@/assets/img/logo.svg" alt="Логотип" class="info-block__logo">
          </a>
        </div>
      </div>
      <MainForm/>
    </div>
    <Footer/>
  </div>
</template>

<script>
import MainForm from "@/components/forms/MainForm.vue";
import Footer from "@/components/Footer.vue";

export default {
components: {Footer, MainForm}
}

</script>

<style scoped>

@font-face {
  font-family: GheaMariam;
  src: url("@/assets/fonts/gheamariam.otf") format("opentype");
  font-style: normal;
}

._container {
  margin: 0 auto;
  padding: 0 86px;
  position: relative;
}

.main-page-wrapper {
  display: flex;
  max-width: 1554px;
  justify-content: space-between;
}

.info-block {
  padding-top: 56px;
}

.info-block__header,
.info-block__description {
  filter: drop-shadow(4px 0px 4px rgba(0, 0, 0, 0.25));
}

.info-block__header {
  font-family: GheaMariam;
  font-weight: 400;
  font-size: 66px;
  line-height: 110%;
  letter-spacing: 0.05em;
  margin-bottom: 50px;
}

.info-block__description {
  font-size: 14px;
  line-height: 150%;
  letter-spacing: 0.05em;
  margin-bottom: 97px;
}

@media (max-width: 1200px) {
  ._container {
    padding: 0 30px;
  }

  .info-block__header {
    font-size: 50px;
    margin-bottom: 30px;
  }

  .info-block__description {
    margin-bottom: 60px;
  }
}

@media (max-width: 1000px) {
  ._container {
    margin: 0 auto;
  }

  .info-block {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 20px;
  }

  .info-block__header {
    text-align: center;
  }

  .info-block__logo-link {
    margin-right: 20px;
  }

  .info-block__wrapper {
    display: flex;
    justify-content: space-between;
    flex-direction: row-reverse;
  }

  .info-block__description {
    font-size: 12px;
    margin-bottom: 0;
  }

  .main-page-wrapper {
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }
}

@media (max-width: 450px) {
  .info-block__header {
    margin-bottom: 20px;
  }

  .info-block__logo-link {
    display: flex;
    justify-content: center;
    margin-right: 0;
  }

  .info-block__wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .info-block__description {
    text-align: center;
    margin-bottom: 20px;
  }

  .info-block__logo {
    width: 60%;
  }

  .info-block__header {
    font-size: 35px;
  }
}
</style>