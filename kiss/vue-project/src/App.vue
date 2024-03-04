<template>
  <div class="container">
    <div class="text-center">
      <h1 class="text-9xl mb-7">❤</h1>
      <h2 v-show="text_image1" class="text-white text-3xl">Do you love me? ❤</h2>

      <div class="image-container">
        <div v-show="marrya" class="space-y-5">
        <img  src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExMTd1OHlzaWQ0Z3F6dTFnZ2w3d2poZ2c4b2lwNGgxMHgzaDIxeXV2byZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/aYjBzdDxOEco0/giphy.gif" alt="">
      <p class="text-2xl">I love you forever 💖</p>
      </div>
        <div v-show="img1" >
          <!-- <img class="gif-image "  src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExY3dxeG5wZm1naGdyNGpxNzI5a2ppNnc2a2NkZTQzYmJscHkxemljaiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/TFwEi08NRQXao/giphy.gif" alt=""> -->
          <div>
            <p class="text-2xl">Yeah I love you too</p>
            <div class="flex justify-center">
              <img class="gif-image "   src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExY3dxeG5wZm1naGdyNGpxNzI5a2ppNnc2a2NkZTQzYmJscHkxemljaiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/TFwEi08NRQXao/giphy.gif" alt="">
            </div>
           
              <p class="text-2xl">Will you marry me? 💑
                <div class="mt-6">
              <button class="btn-yess " @click="funcMarry">Yes</button>
            </div>
            </p>
          </div>
        </div>
        <img v-show="img2" class="gif-image" src="https://media4.giphy.com/media/HMSLfCl5BsXoQ/giphy.gif?cid=ecf05e472w08iycweu2ojbdjohxjvlfsfwqqzxf6gsa3tu7m&ep=v1_gifs_related&rid=giphy.gif&ct=g" alt="">
        <img v-show="img3" class="gif-image" src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExbHQ3dWl5dG04NjZ0emk4ZGhhOGVtb3lsOHZpa3o1bWJrZThuZmtjZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/S3a3lkSqW6Ve8/giphy.gif" alt="">
        <img v-show="img4" class="gif-image" src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExY2pzYXd5MHIxaXM3eWxrNGZ5OWpjMG1wYWt3NzRvMDMzOTZqeGNreSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/dEu4TtBWR5t0ocD97d/giphy.gif" alt="">
      </div>

      <div v-show="bottonX" class="buttons">
        <p v-show="text_no" class="text-2xl">Click yes please ❤</p>
        <button class="btn-yes" @click="funyes">Yes</button>
        <button class="btn-no" @click="funno">No</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref ,onMounted} from 'vue';

const marrya = ref(false);
const text_no = ref(false);
const img1 = ref(false);
const img2 = ref(false);
const img3 = ref(false);
const img4 = ref(false);
const text_image1 = ref(false);
const bottonX = ref(true);

onMounted(()=>{
      text_image1.value = true
})

const funcMarry = () => {
  marrya.value = true;
  img1.value = false;
  bottonX.value = false;
};

const imgNO = () => {
  img2.value = true;
  img3.value = true;
  img4.value = true;
  img1.value = false;
  text_no.value = true;
  text_image1.value = false;
};

const funyes = () => {
  img1.value = true;
  img2.value = false;
  img3.value = false;
  img4.value = false;
  text_image1.value = false;
  text_no.value = false;
  bottonX.value = false
};

const funno = () => {
  imgNO();
};
</script>

<style scoped>
/* Container Styles */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

/* Text Styles */
.text-center {
  text-align: center;
}

.text-9xl {
  font-size: 9rem;
}

.text-3xl {
  font-size: 1.875rem;
}

/* Image Container Styles */
.image-container {
  display: flex;
  justify-content: center;
  margin-top: 20px;
  flex-wrap: wrap; /* Allow images to wrap to next line */
}

/* Button Styles */
.buttons {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.btn-yes,
.btn-no,
.btn-yess {
  padding: 10px 20px;
  margin: 0 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100px;
}

.btn-yess {
  background-color: palevioletred;
}

.btn-yes {
  background-color: #4caf50;
  color: white;
  transition: transform 0.5s ease; /* Add transition effect */
}

.btn-no {
  background-color: #f44336;
  color: white;
}

/* Image Styles */
.gif-image {
  width: 200px; /* Fixed width to maintain consistent size */
  height: auto;
  margin: 10px; /* Add some margin between images */
  
}

/* Responsive Styles */
@media screen and (max-width: 768px) {
  .gif-image {
    width: 150px; /* Adjust width for smaller screens */
  }

  .text-9xl {
    font-size: 6rem; /* Decrease font size for smaller screens */
  }

  .text-3xl {
    font-size: 1.5rem; /* Decrease font size for smaller screens */
  }
}
</style>
