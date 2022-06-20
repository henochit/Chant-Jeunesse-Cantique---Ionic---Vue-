<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <div id="container">
        <strong>Chant O jeunesse</strong>
        <p>Jeune pour christ</p>
        <ion-spinner name="dots"></ion-spinner>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage, IonSpinner } from "@ionic/vue";
import { defineComponent } from "vue";
import { onMounted } from "vue";
import { useRouter } from "vue-router";

export default defineComponent({
  name: "SplashScreen",
  components: {
    IonContent,
    IonPage,
    IonSpinner,
  },
  setup() {
    const router = useRouter();

    function loadHomePage() {
      router.push("/home");
    }

    onMounted(() => {
      setTimeout(loadHomePage, 5000);
    });
  },
});
</script>

<style scoped>
#container {
  text-align: center;

  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}
</style>
