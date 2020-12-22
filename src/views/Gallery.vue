<template>
  <v-container style="padding-top:64px">
    <v-row style="padding:32px">
      <v-col>
        <h2 class="text-center">GALLERY</h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        v-for="(image, i) in images"
        :key="i"
        class="d-flex child-flex "
        cols="6"
        md="4"
      >
        <div class="image_item">
          <v-img
            :src="image"
            :lazy-src="`https://picsum.photos/10/6?image=${i * 5 + 10}`"
            aspect-ratio="1"
            class="d-flex child-flex mt-0"
            @click="onClick(i)"
          >
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular
                  indeterminate
                  color="grey lighten-5"
                ></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </div>
      </v-col>
    </v-row>
    <vue-gallery-slideshow
      :images="images"
      :index="index"
      @close="index = null"
      id="show"
      class="margin-top"
    >
    </vue-gallery-slideshow>
  </v-container>
</template>

<script>
import VueGallerySlideshow from "vue-gallery-slideshow";

export default {
  components: {
    VueGallerySlideshow,
  },
  methods: {
    onClick(i) {
      this.index = i;
    },
  },
  data() {
    return {
      images: [
        require("@/assets/gallery/ga8.jpg"),
        require("@/assets/gallery/ga11.jpg"),
        require("@/assets/gallery/ga3.jpg"),
        require("@/assets/gallery/ga12.jpg"),
        require("@/assets/gallery/ga5.jpg"),
        require("@/assets/gallery/ga6.jpg"),
        require("@/assets/gallery/ga4.jpg"),
        require("@/assets/gallery/ga10.jpg"),
      ],
      index: undefined,
    };
  },
};
</script>
<style lang="scss" scoped>
.d-flex {
  margin-top: 5%;
}

.vgs__container {
  margin-top: 7% !important;
}
.image_item {
  cursor: pointer;
  overflow: hidden;
  border-radius: 6px;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  &:hover {
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
    transform: translateY(-2px);
  }
}
</style>
