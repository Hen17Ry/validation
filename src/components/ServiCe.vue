<template>
    <div>
      <h1 style="text-align: center; margin-bottom: 100px; font-size: 50px;">Our Service</h1>
      <div class="service-container">
        <div class="service-image-wrapper">
          <img :src="serviceImage" alt="Service Image" class="service-image">
        </div>
        <div class="service-text">
          <h2>{{ serviceTitle }}</h2>
          <p>{{ serviceDescription }}</p>
      </div>
    </div>
    </div>
</template>

    <script>
        export default {
        name: 'ServiceCard',
        data() {
            return {
            serviceImage: '/servi.avif',
            serviceTitle: 'Our Amazing Service',
            serviceDescription: 'Welcome to our platform dedicated to the verification and authentication of prepaid cards. We offer a fast, secure and reliable service to ensure that your prepaid cards are valid and authentic. Whether for gift cards or payment cards, our service guarantees you complete peace of mind.'
            };
        }
        };
    </script>

<style scoped>
.service-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center; /* Center the service element horizontally */
  background: white;
  border-radius: 15px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  width: 80%;
  max-width: 1200px; /* Increase the maximum width */
  margin: 20px auto; /* Center the container */
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.service-container:hover {
  transform: scale(1.05);
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.3);
}

.service-image-wrapper {
  flex: 1;
  overflow: hidden;
}

.service-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease-in-out;
}

.service-container:hover .service-image {
  transform: scale(1.1);
}

.service-text {
  flex: 2;
  padding: 40px; /* Increase padding */
  text-align: left;
}

.service-text h2 {
  margin-top: 0;
  font-size: 2rem; /* Increase font size */
  color: #333;
}

.service-text p {
  font-size: 1.2rem; /* Increase font size */
  color: #666;
}

@media (max-width: 768px) {
  .service-container {
    flex-direction: column;
    max-width: 100%; /* Adjust the max width for smaller screens */
  }
  .service-image-wrapper {
    width: 100%;
    height: 300px; /* Adjust the height for smaller screens */
  }
  .service-text {
    padding: 20px; /* Adjust padding for smaller screens */
  }
}
</style>
