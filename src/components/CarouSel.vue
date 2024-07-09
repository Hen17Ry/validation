<template>
  <div class="pic-ctn">
    <img src="/1.jpg" alt="" class="pic">
    <img src="/2.jpg" alt="" class="pic">
    <img src="/3.jpg" alt="" class="pic">
    <img src="/4.jpg" alt="" class="pic">
    <img src="/5.avif" alt="" class="pic">
  </div>
</template>

<script>
export default {
  
};
</script>

<style scoped>
.pic-ctn {
  position: absolute;
   /* Centrer horizontalement et verticalement */
  width: 100%; /* Réglage de la largeur du conteneur */
  height: 500px; /* Réglage de la hauteur des images */
  overflow: hidden; /* Masquage du débordement pour éviter les sauts de ligne */
  margin-top: 20px;
}

.pic-ctn > img {
  position: absolute;
  width: 400px; /* Largeur des images */
  height: 500px; /* Hauteur des images */
  opacity: 0;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: display 20s infinite; /* Animation sur une durée de 20 secondes */
}

@keyframes display {
  0% {
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

/* Décalage des animations pour chaque image */
.pic-ctn > img:nth-child(2) {
  animation-delay: 5s; /* Décalage de l'animation de 5 secondes pour la deuxième image */
}
.pic-ctn > img:nth-child(3) {
  animation-delay: 10s; /* Décalage de l'animation de 10 secondes pour la troisième image */
}
.pic-ctn > img:nth-child(4) {
  animation-delay: 15s; /* Décalage de l'animation de 15 secondes pour la quatrième image */
}
.pic-ctn > img:nth-child(5) {
  animation-delay: 20s; /* Décalage de l'animation de 20 secondes pour la cinquième image */
}
</style>
