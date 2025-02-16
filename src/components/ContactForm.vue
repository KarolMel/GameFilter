<script>
</script>

<template>
  <div>
    <section class="contact-info">
      <h1>Skicka medelande till mig</h1>
      <form id="contact-form">
        <img class="mail-message" src="../../assets/icons/mailMessage.png" alt="Mail message">
        <div class="form">
          <input type="text" id="name" name="name" placeholder="Username">
          <input type="email" id="emial" name="email" placeholder="Email">
          <textarea id="message" name="message" placeholder="Message"></textarea>
          <input class="send-button" type="submit" value="Skicka ->" />
        </div>
      </form>
    </section>
  </div>
</template>

<style scoped>
.contact-info {
  align-items: center;
  display: flex;
  flex-direction: column;
  height: 70vh;
  justify-content: center;
  text-align: center;
  width: 100%;
}

div {
  align-items: center;
  display: flex;
  height: 85vh;
  justify-content: center;
  margin: 10px 0 10px 10px;
  width: 99%;
}

.form {
  align-items: center;
  display: flex;
  flex-direction: column;
  height: auto;
  justify-content: center;
  width: 50%;
}

h1 {
  color: white;
}

input {
  border: none;
  border-radius: 20px;
  height: 35px;
  margin: 20px;
  outline: none;
  width: 60%;
}

input:focus {
  border: solid 2px;
  border-color: #007bff;
  box-shadow: 0 4px 12px rgba(0, 123, 255, 0.2);
}

.mail-message {
  height: 350px;
  width: 350px;
}

.send-button {
  background-color: rgb(24, 129, 24);
  color: white;
  cursor: pointer;
  font-family: cursive;
  font-size: 18px;
  transition: all 0.4s ease-in-out;
  width: 150px;
}

.send-button:hover {
  background-color: rgb(74, 112, 74);
  color: black;
}

textarea {
  height: 13vh;
  width: 60%;
}

::placeholder {
  color: rgb(77, 77, 77);
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 16px;
  font-weight: bold;
}

#contact-form {
  align-items: center;
  background: rgba(37, 88, 58, 0.226);
  background: linear-gradient(0deg, rgba(4, 37, 131, 0.658) 18%, rgba(139, 112, 165, 0.356) 82%);
  border-radius: 20px;
  display: flex;
  height: 400px;
  justify-content: space-evenly;
  width: 900px;
}

@media (min-width: 360px) and (max-width: 980px) {
  .contact-info {
    height: auto;
  }

  #contact-form {
    align-items: center;
    display: flex;
    flex-direction: column;
    height: 80vh;
    justify-content: center;
    width: 90%;
  }

  .mail-message {
    height: 170px;
    width: 170px;
  }

  input {
    width: 300px;
  }

  textarea {
    width: 300px;
  }
}
</style>