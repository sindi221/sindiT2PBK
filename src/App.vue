<template>
  <div class="container">
    <header>
      <h1>{{ pageTitle }}</h1>
    </header>
    <main>
      <section class="hero">
      <h2> 
        "Discover luxurious scents that perfectly complement your style and preferences."</h2>
      <input v-model="text" placeholder="Type here">
      <p>{{ text }}</p>
    </section>

    <section class="features">
        <div class="feature" :class="{ highlighted: isHighlighted }" @click="toggleHighlight">

          <img src="./assets/P3-removebg-preview.png" alt="Feature 1" />
          <h3>
            ZARA <br />
            RED VANILLA
          </h3>
          <p>
            Wewangian canggih, hangat, dan rempah dengan aroma nuansa bunga dan rasa manis. Sebuah
            buket dari bunga iris dan botan merah elegan, dikombinasikan dengan kesegaran aroma
            jeruk keprok dan sentuhan rasberi yang manis dan lembut, menyatu dengan aroma vanili.
          </p>
        </div>

        <div class="feature">
          <img src="./assets/P4-removebg-preview.png" alt="Feature 2" />
          <h3>
            ZARA <br />
            Night Pour Homme II
          </h3>
          <p>
            Parfum Zara Night Pour Homme II ini memiliki campuran wangi buah bergamot, wangi amber
            (campuran aroma vanili, bunga dan aroma kayu) dan wangi lavender. Campuran wewangian
            tersebut menimbulkan rasa segar, nocturnal dan sporty.
          </p>
        </div>

        <div class="feature">
          <img src="./assets/P2-removebg-preview.png" alt="Feature 3" />
          <h3>
            ZARA <br />
            NUDE BOUQUET
          </h3>
          <p>
            Eau de parfum. Piramida wangi termasuk aroma ceri, peony, dan vanili. Merupakan aroma
            segar, nyaman, dan bersemangat.
          </p>
        </div>
      </section>
      <section class="testimonial">
        <blockquote>
          <p>"This perfume website is amazing! It has everything I need and more."</p>
          <footer>- "Fragrance Enthusiast Hub"</footer>
        </blockquote>
      </section>
    </main>
    <footer>
      <p>&copy; 2024 Our Website.SINDI MAHARANI .</p>
    </footer>
    <div class="modal" v-if="showModal" @click="toggleModal">
      <div class="modal-content" @click.stop>
        <span class="close" @click="toggleModal">&times;</span>
        <h2>About Us</h2>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  data() {
    return {
      pageTitle: 'Welcome to Our Website!',
      showModal: false,
      isHighlighted: false,
      text: ''
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted
    }
  }
}
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

main {
  padding: 20px;
}

.hero {
  text-align: center;
  margin-bottom: 40px;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.2rem;
  margin-bottom: 30px;
}

.features {
  display: flex;
  justify-content: space-around;
  margin-bottom: 40px;
}

.feature {
  text-align: center;
  flex: 1;
}

.feature img {
  max-width: 500px;
}

.feature h3 {
  margin-top: 20px;
  font-size: 1.5rem;
}

.testimonial {
  text-align: center;
  margin-bottom: 40px;
}

.testimonial blockquote {
  font-size: 1.5rem;
}

.testimonial footer {
  margin-top: 10px;
  font-style: italic;
}

footer {
  background-color: #333;
  color: white;
  padding: 20px;
  text-align: center;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.highlighted {
  background-color: yellow;
}
</style>