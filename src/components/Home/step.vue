<template>
  <div class="root">
    <v-row no-gutters class="details">
      <v-col cols="12" md="6" class="leftarea">
        <div>
          <v-expansion-panels accordion>
            <v-expansion-panel v-for="(item, i) in items" :key="i">
              <v-expansion-panel-header
                :expand-icon="item.icon"
                @click="handleImg(i)"
              >
                {{ item.step }}
              </v-expansion-panel-header>
              <v-expansion-panel-content>
                {{ item.content }}
              </v-expansion-panel-content>
            </v-expansion-panel>
          </v-expansion-panels>
        </div>
      </v-col>

      <v-col cols="12" md="6" class="rightarea">
        <div class="image">
          <img
            src="@/assets/services/step/default.jpg"
            alt="navatan1"
            v-if="this.visible == 10"
          />
          <img
            src="@/assets/services/step/step1.jpg"
            alt="navatan1"
            v-if="this.visible == 0"
          />

          <img
            src="@/assets/services/step/step2.jpg"
            alt="navatan2"
            v-if="this.visible == 1"
          />

          <img
            src="@/assets/services/step/step3.jpg"
            alt="navatan3"
            v-if="this.visible == 2"
          />

          <img
            src="@/assets/services/step/step4.jpg"
            alt="navatan4"
            v-if="this.visible == 3"
          />
          <img
            src="@/assets/services/step/step5.jpg"
            alt="navatan4"
            v-if="this.visible == 4"
          />
          <img
            src="@/assets/services/step/step6.jpg"
            alt="navatan4"
            v-if="this.visible == 5"
          />
          <img
            src="@/assets/services/step/step7.jpg"
            alt="navatan4"
            v-if="this.visible == 6"
          />
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  methods: {
    handleImg(i) {
      this.visible = i;
    },
  },
  data: () => ({
    visible: 10,
    items: [
      {
        step: "Bước 1: Bôi kem dưỡng",
        icon: "mdi-bottle-tonic",
        content:
          "Bôi kem dưỡng, kem dưỡng là vật dụng không thể thiếu khi tanning, giúp lớp da đều màu, bóng loáng",
      },
      {
        step: "Bước 2: Kết nối nhạc",
        icon: "mdi-bluetooth-audio",
        content: "Kết nối playlist nhạc yêu thích của mình với giường tanning",
      },
      {
        step: "Bước 3: Đeo kính râm",
        icon: "mdi-sunglasses",
        content: "Đeo kính râm Navatan cung cấp để bảo vệ mắt",
      },
      {
        step: "Bước 4: Thư giãn",
        icon: "mdi-bed",
        content: "Nằm thư giãn trong vòng từ 15 đến 20 phút",
      },
      {
        step: "Bước 5: Chụp ảnh feedback",
        icon: "mdi-camera",
        content: "Mọi người nhớ chụp những tấm ảnh feedback và ..",
      },
      {
        step: "Bước 6: Ngắm thành quả",
        icon: "mdi-mirror",
        content: "Soi gương chụp ảnh và ngắm thành quả",
      },
      {
        step: "Bước 7: Gửi ảnh cho Navatan",
        icon: "mdi-instagram",
        content: "Hãy gửi ảnh về cho Navatan để nhận nhiều ưu đãi nha",
      },
    ],
  }),
};
</script>

<style scoped>
.v-expansion-panel-header {
  font-family: "Dancing Script", cursive !important;
  font-size: 30px;
}
.title {
  margin-left: 5%;
  font-size: 30px !important;
  text-align: center;
  margin-bottom: 5%;
}

img {
  border-radius: 50%;
}

.image {
  text-align: -webkit-center;
  margin-left: 10%;
}

.root {
  margin-top: 0%;
  margin-bottom: 3%;
}

.v-expansion-panels {
  z-index: unset !important;
  margin-left: 10%;
}

.v-expansion-panel {
  margin-top: 1% !important;
}
</style>
