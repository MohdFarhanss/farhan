<template>
  <div class="container">
    <header>
      <h1>{{ pageTitle }}</h1>
    </header>
    <main>
      <section class="hero">
      <h2> 
"Discover the dream car that fits your style and needs."</h2>
      <input v-model="text" placeholder="Type here">
      <p>{{ text }}</p>
    </section>
      <section class="features">
        <div class="feature" :class="{ highlighted: isHighlighted }" @click="toggleHighlight">
          <img src="./assets/f1-removebg-preview.png" alt="Feature 1" />
          <h3>RUBICON</h3>
          
          <p>
            Jeep® Wrangler menjadi salah satu kendaraan roda empat paling ikonik yang bisa anda miliki 
            melalui DAS Indonesia. Jeep varian Wrangler ini bisa anda dapatkan dalam berbagai varian,
             dimana Rubicon menjadi varian dengan kemampuan offroad paling baik sekaligus tertinggi, 
            Sahara menjadi varian yang mewah, dan Sport menjadi varian untuk anda yang suka kepraktisan.
          </p>
        </div>

        <div class="feature" :class="{ highlighted: isHighlighted }" @click="toggleHighlight">
          <img src="./assets/f2-removebg-preview.png" alt="Feature 2" />
          <h3>
           CIVIC TURBO
          </h3>
          <p>
            Versi hatchback Honda Civic Turbo memang kerap dimodifikasi 
            karena punya desain standar yang keren dan sporty.
             Berbagai konsep modifikasi bisa disematkan ke Honda Civic Turbo, 
             namun umumnya bersolek sporty atau dibuat agresif gaya racing.
             Sporty Mantap Mengusung Jubah Kuning Spoon".</p>
        </div>

        <div class="feature" :class="{ highlighted: isHighlighted }" @click="toggleHighlight">
          <img src="./assets/f3-removebg-preview.png" alt="Feature 3" />
          <h3>
            LAMBORGHINI <br> AVENTADOR SJV
          </h3>
          <p>
            Supercar dengan unit sangat terbatas ini memiliki banderol sebesar Rp 22 miliar! 
            Mobil eksotis asal Italia dilengkapi dengan mesin berkapasitas 6.500 cc dengan konfigurasi V12.
             Bahkan top speed-nya diklaim bisa menembus angka 350 km/jam!
          </p>
        </div>
      </section>
      <section class="testimonial">
        <blockquote>
          <p>"Explore our collection of luxury cars"</p>
          <footer>"Luxury Car Enthusiast Hub"</footer>
        </blockquote>
      </section>
    </main>
    <footer>
      <p>&copy; 2024 Our Website.MOHD.FARHAN.S .</p>
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
