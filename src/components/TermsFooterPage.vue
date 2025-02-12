<template>
  <div class="container pt-0">
    <div class="footer-text">
      <p class="p-0 m-0">
        By continuing , you agree to Taskly
        <span>Terms of Service. Privacy Policy and Cookies Policy.</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TermsFooterPage",
};
</script>

<style scoped>
.footer-text {
  text-align: center;
  align-items: center;
}

.footer-text p {
  font-size: 9px;
  color: #767676;
  font-weight: 400;
}

.footer-text p span {
  font-weight: 700;
  text-decoration: underline;
  text-decoration-style: solid;
}
</style>
