<template>
  <div class="_container">
    <div class="main-page-wrapper">
      <div class="info-block">
        <h1 class="info-block__header">send<br>a request</h1>
        <p class="info-block__description">leave your contacts<br>and we will contact<br>you as soon as possible</p>
        <a href="#" class="info-block__logo-link">
          <img src="@/assets/img/logo.svg" alt="Логотип" class="info-block__logo"></a>

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
  font-size: 66px;
  font-weight: 500;
  line-height: 110%;
  letter-spacing: 3px;
  margin-bottom: 50px;
}

.info-block__description {
  font-size: 14px;
  line-height: 150%;
  letter-spacing: 1px;
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
  }
  .info-block__header,
  .info-block__description
  {
    text-align: center;
  }
  .main-page-wrapper {
    align-items: center;
    flex-direction: column;
  }
}
@media (max-width: 600px) {
  .info-block__header {
    font-size: 35px; }
}
</style>