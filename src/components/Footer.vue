<template>
  <div class="footer-wrapper">
    <div class="links">
      <p class="footer-text">Our links and contacts</p>
      <a
        href="https://chrome.google.com/webstore/detail/behance-saver/pcgmjcfekkppafhcjbpajfgakmlmnbfn?utm_source=ext_sidebar&hl=ru"
        class="footer-link"
        target="_blank"
        ><img src="@/chrome.png" alt="Chrome"
      /></a>
      <a
        href="https://addons.mozilla.org/ru/firefox/addon/extension-for-behance-images/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search"
        class="footer-link"
        target="_blank"
        ><img src="@/firefox.png" alt="Firefox"
      /></a>
      <a href="https://t.me/QwertykQwertov" class="footer-link" target="_blank"
        ><img src="@/telegram.png" alt="Telegram"
      /></a>
      <a href="https://pay.cloudtips.ru/p/108a3cf6" class="footer-link" target="_blank"
        ><img src="@/money.png" alt="Telegram"
      /></a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-wrapper {
  width: 100%;
  margin-top: 30px;
}
.links {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
.footer-text {
  margin: 0;
}
.footer-link {
  &:hover > img {
    transform: scale(1.2);
  }
}
img {
    width: 33px;
    height: 33px;
  }

@media (max-width: 430px) {
  .links {
    flex-wrap: wrap;
  }
  .footer-text {
    width: 95%;
    text-align: center;
  }
}
</style>
