<template>
  <div class="root">
    <v-carousel
      cycle
      hide-delimiter-background
      show-arrows-on-hover
      height="700px"
    >
      <v-carousel-item
        v-for="(slide, i) in items"
        :src="slide.src"
        :key="i"
        transition="fade-transition"
      >
        <v-container class="img_cover" fill-height>
          <v-layout align-center>
            <v-flex>
              <v-img
                class="logo"
                max-height="100"
                max-width="200"
                src="@/assets/home/logo.png"
              ></v-img>
              <h3 class="display-3">{{ slide.title }}</h3>
              <button
                v-if="customerName"
                class="slide-cta-btn"
                @click="showScheduleModal"
              >
                Đặt lịch ngay
              </button>
              <button
                v-if="!customerName"
                class="slide-cta-btn"
                @click="showWhenNotLogin"
              >
                Đặt lịch ngay
              </button>
            </v-flex>
          </v-layout>
        </v-container>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
import swal from "sweetalert";

export default {
  name: "slides",
  components: {},
  methods: {
    showScheduleModal() {
      this.$store.commit("toggleScheduleModal", true);
    },

    showWhenNotLogin() {
      swal("Rất tiếc!", "Bạn phải đăng nhập đã nhé !", "warning");
    },
  },
  data() {
    return {
      customerName: localStorage.getItem("customerName"),
      items: [
        {
          title: "Tanning Studio đầu tiên tại Việt Nam",
          src: require("@/assets/home/cover_1.png"),
        },
        {
          title: "Love your body, love your skin",
          src: require("@/assets/home/cover_2.png"),
        },
        {
          title: "An toàn hiệu quả nhanh chóng",
          src: require("@/assets/home/cover_6.jpg"),
        },
        {
          title: "Khỏe mạnh gợi cảm thời thượng",
          src: require("@/assets/home/cover_7.jpg"),
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.display-3 {
  font-family: "Montserrat" !important;
  font-weight: bold !important;
  text-transform: uppercase;
  margin-block: 3% !important;
  font-size: 275% !important;
}

.slide-cta-btn {
  color: #ffffff;
  background: rgba(197, 197, 197, 0.5);
  border: 1px solid #ffffff;
  border-radius: 2px;
  padding: 12px 24px;
  text-transform: uppercase;
  font-weight: bold;
  background-color: transparent;
  font-size: larger;
  transition-duration: 0.4s;
  margin-left: 0% !important;
}
.slide-cta-btn:hover {
  color: black;
  background: rgba(197, 197, 197, 0.5);
  border: 1px solid #ffffff;
  border-radius: 2px;
  padding: 12px 24px;
  text-transform: uppercase;
  font-weight: bold;
  background-color: white;
  font-size: larger;
}

@keyframes text-shadow-drop-center {
  0% {
    text-shadow: 0 0 0 transparent;
  }
  100% {
    text-shadow: 0 0 18px rgba(0, 0, 0, 0.35);
  }
}

@keyframes slide-cta-btn {
  0% {
    transform: translate(0);
  }
  20% {
    transform: translate(-2px, 2px);
  }
  40% {
    transform: translate(-2px, -2px);
  }
  60% {
    transform: translate(2px, 2px);
  }
  80% {
    transform: translate(2px, -2px);
  }
  100% {
    transform: translate(0);
  }
}
</style>
