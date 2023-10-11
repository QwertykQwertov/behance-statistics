<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <div class="footer-wrapper">
    <div class="links">
      <p class="footer-text">Our links and contacts</p>
      <a
        href="https://chrome.google.com/webstore/detail/behance-saver/pcgmjcfekkppafhcjbpajfgakmlmnbfn?utm_source=ext_sidebar&hl=ru"
        class="footer-link"
        target="_blank"
        ><img src="../assets/chrome.svg" alt="Chrome"
      /></a>
      <a
        href="https://addons.mozilla.org/ru/firefox/addon/extension-for-behance-images/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search"
        class="footer-link"
        target="_blank"
        ><img src="../assets/firefox.svg" alt="Firefox"
      /></a>
      <a href="https://t.me/QwertykQwertov" class="footer-link" target="_blank"
        ><img src="../assets/telegram.svg" alt="Telegram"
      /></a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-wrapper {
  width: 100%;
  margin-top: 50px;
}
.links {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
.footer-text {
  font-size: 38px;
  margin: 0;
}
.footer-link {
  &:hover > img {
    transform: scale(1.2);
  }
}
</style>
