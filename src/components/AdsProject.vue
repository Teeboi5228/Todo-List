<template>
  <!-- container -->
  <div class="container">
    <!-- advert-button -->
    <div class="advert-button">
      <button>Skip</button>
    </div>

    <!-- advert-img -->
    <div class="advert-img">
      <img :src="img" alt="" />
    </div>

    <!-- welcome -->
    <div class="welcome">
      <h3>Welcome to <span>Taskly</span></h3>
      <p>{{ content[imgIndex] }}</p>

      <!-- welcome-btn -->
      <div class="welcome-btn">
        <button @click="nextImage">Next</button>
      </div>

      <!-- scroll -->
      <div class="scroll">
        <div class="scroll1" :class="imgIndex === 0 ? 'active' : ''"></div>
        <div class="scroll2" :class="imgIndex === 1 ? 'active' : ''"></div>
        <div class="scroll3" :class="imgIndex === 2 ? 'active' : ''"></div>
      </div>
    </div>

    <footer>
      <TermsFooterPageVue />
    </footer>
  </div>
</template>

<script>
import TermsFooterPageVue from "./TermsFooterPage.vue";
export default {
  name: "AdsProjectVue",
  components: {
    TermsFooterPageVue,
  },
  data() {
    return {
      images: [
        require("@/assets/ads1.png"),
        require("@/assets/ads2.png"),
        require("@/assets/ads3.png"),
      ],
      content: [
        "Your Personal Task Manager To Help You Stay Organised And Productive",
        "Stay on top of your tasks and boost your productivity with your ultimate personal organizer",
        "Effortlessly manage your tasks and achieve more.",
      ],
      imgIndex: 0,
    };
  },
  computed: {
    img() {
      return this.images[this.imgIndex];
    },
  },
  methods: {
    nextImage() {
      this.imgIndex = (this.imgIndex + 1) % this.images.length;
    },
  },
};
</script>

<style scoped>
.container {
  padding: 10px 12px;
}

/* advert-text */
.advert-button {
  position: relative;
}

.advert-button button {
  margin-top: 20px;
  position: absolute;
  top: 0;
  left: 80%;
  border: none;
  outline: none;
  background: transparent;
  color: #727476;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.5s ease-in-out;
}

.advert-img {
  width: 100%;
  text-align: center;
  margin: 20px 0 15px;
}

.advert-img img {
  width: 70%;
}

/* welcome */
.welcome {
  text-align: center;
}

.welcome h3 {
  color: #000000;
  font-size: 18px;
  font-weight: 500;
}

.welcome h3 span {
  color: #219afd;
  font-weight: 600;
  font-size: 18px;
}

.welcome p {
  font-size: 12px;
  font-weight: 400;
  line-height: 18px;
  color: #000000;
}

.welcome-btn {
  width: 100%;
  margin-bottom: 3%;
}

.welcome-btn button {
  background: #09203e;
  padding: 12px 120px;
  border-radius: 25px;
  border: none;
  outline: none;
  color: #ffffff;
  font-size: 16px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.5s ease-in-out;
}

/* scroll */
.scroll {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 0 5px;
  width: 100%;
  height: 5vh;
  margin-bottom: 10px;
}

.scroll1,
.scroll2,
.scroll3 {
  width: 10px;
  height: 10px;
  border-radius: 100px;
  background: #d9d9d9;
}

.active {
  background: #000;
}

footer {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
}

@media (min-height: 500px) {
  .advert-img img {
    width: 90%;
  }

  .advert-img {
    margin: 40px 0 15px;
  }
}

@media (min-height: 600px) {
  .advert-img img {
    width: 100%;
  }

  .advert-img {
    margin: 60px 0 15px;
  }

  .advert-button button {
    margin-top: 50px;
  }

  footer {
    bottom: 10px;
  }
}

@media (min-height: 800px) {
  .advert-button button {
    margin-top: 70px;
  }

  footer {
    bottom: 30px;
  }
}

@media (min-width: 320px) {
  .container {
    padding: 10px 16px;
  }
}
</style>
