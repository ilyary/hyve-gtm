<template>
  <NuxtPage />
</template>

<script setup>
import "bootstrap/scss/bootstrap.scss";

import "@/styles/async.scss";
//import("@/styles/async.scss");

if (import.meta.env.SSR) {
  useHead({
    title: "GTM Integration",
    script: [
      {
        src: "https://cdn.cookielaw.org/consent/d98adfc6-eaf5-4d0d-934b-bd944151d81e-test/otSDKStub.js",
        "data-domain-script": "d98adfc6-eaf5-4d0d-934b-bd944151d81e-test",
        charset: "UTF-8",
      },
      // {
      //   src: "https://cdn.cookielaw.org/scripttemplates/otSDKStub.js",
      //   "data-domain-script": "d98adfc6-eaf5-4d0d-934b-bd944151d81e",
      //   charset: "UTF-8",
      // },
      {
        children: `function OptanonWrapper() {
        }`,
      },
      {
        children: `(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
          new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
          j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
          'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
          })(window,document,'script','dataLayer','GTM-W7SMGWD');`,
      },
    ],
  });
}
</script>

<style lang="scss">
$fa-font-path: "@fortawesome/fontawesome-free/webfonts";
@import "@fortawesome/fontawesome-free/scss/fontawesome";
</style>
