<template>
  <h1>Contact Me</h1>

  <form name="contact" method="POST" @submit.prevent="handleSubmit" class="form">
    <input type="hidden" name="form-name" value="contact" />

    <label>Name:</label>
    <input type="text" name="name" v-model="form.name" required />
    <br /><br />

    <label>Email:</label>
    <input type="email" name="email" v-model="form.email" required />
    <br /><br />

    <label>Message:</label>
    <textarea name="message" v-model="form.message" required></textarea>

    <button type="submit">Send</button>
  </form>

</template>

<script setup>
import { ref } from 'vue'

const encode = (data) =>
  Object.keys(data)
    .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
    .join('&')

async function handleSubmit() {
  try {
    await fetch('/', {
      method: 'POST',
      headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
      body: encode({ 'form-name': 'contact', ...form.value }),
    })
    submitted.value = true
    form.value = { name: '', email: '', message: '' }
  } catch (e) {
    error.value = true
  }
}
</script>
<style>
.form {
  border: 2px solid #5c4033; 
  background-color:  #cfc8bf; 
  padding: 50px;
  width: 600px;
  margin: auto;
  border-radius: 50px;
}

form label {
  font-weight: bold;
  color: #3b2a1a;
}

form input {
  width: 100%;
  padding: 10px;
  border: 1px solid #5c4033;
  border-radius: 5px;
}

form textarea {
  width: 100%;
  height: 150px; 
  padding: 8px;
  border: 1px solid #5c4033;
  border-radius: 5px;
}

form button {
  margin-top: 20px;
  padding: 10px;
  width: 100%;
  background-color: #5c4033;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

form button:hover {
  background-color: #8b6b4f;
}

</style>