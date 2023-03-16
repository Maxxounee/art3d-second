<template>
  <div class="footer">
    <a href="#" class="footer__name">2022 Luxury Residence</a>
    <a href="#" class="footer__policy">Privacy Policy</a>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
a:hover {
  text-decoration: underline;
}

.footer {
  padding: 157px 0 90px;
}

.footer__name,
.footer__policy {
  font-size: 12px;
  letter-spacing: 1px;
  line-height: 150%;
  text-decoration: none;
}

.footer__name {
  color: #FF69B4;
  margin-right: 211px;
}

@media (max-width: 1000px) {
  .footer {
    padding: 100px 0 30px;
    display: flex;
    justify-content: center;
  }

  .footer__name {
    margin-right: 50px;
  }
}

@media (max-width: 600px) {
  .footer__name,
  .footer__policy {
    text-align: center;
    font-size: 10px;
  }
}
</style>