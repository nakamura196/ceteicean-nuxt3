<script setup lang="ts">
import CETEI from "CETEIcean";

const teiHTML = ref<string>("");

const CETEIcean = new CETEI();
CETEIcean.getHTML5(
  "https://raw.githubusercontent.com/TEIC/CETEIcean/master/test/testTEI.xml",
  function (data: HTMLElement) {
    teiHTML.value = data.outerHTML;
  }
);
</script>
<template>
  <div>
    TEI would go here...
    <div id="tei" v-html="teiHTML" />
  </div>
</template>
