<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <div id="container">
        <ion-searchbar
          show-cancel-button="focus"
          placeholder="Recherche de cantique"
        ></ion-searchbar>
        <ion-list>
          <ion-item href="#" :key="lyric.id" v-for="lyric in lyrics">
            <ion-label> {{ lyric.title }}</ion-label>
          </ion-item>
        </ion-list>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonPage, IonSearchbar } from "@ionic/vue";
import { defineComponent } from "vue";
import { onMounted } from "vue";
import { lyrics } from "../store/lyrics";

export default defineComponent({
  name: "HomePage",
  components: {
    IonContent,
    IonPage,
    IonSearchbar,
  },
  setup() {
    let lyricsFiltered = lyrics;

    onMounted(() => {
      console.log("mounted in the composition api!");
    });

    return {
      lyrics: lyricsFiltered,
    };
  },
});
</script>

<style scoped></style>
