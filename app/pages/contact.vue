<template>
  
    <h1>Contact Me</h1>
    <h3> 🏠Address</h3>
    <p>
       Ntemi Piliso St & Gwigwi Mrwebi St
       <br>
       Brickfields 904
       <br>
       Newtown
       <br>
       Johannesburg
       <br>
       2113
    </p>

        <h3>📧Email</h3>
    <p>
       u25571258@tuks.co.za
       <br>
       ntsika.tshuma.sa@gmail.com
    </p>

        <h3>☎️Phone Number</h3>
    <p>
       (+27) 65-104-2114
       <br>
       (+27) 73-194-8241
       <br>
       <br>
    </p>

<form name="contact" method="POST" data-netlify="true" class="form">
      
      <input type="hidden" name="form-name" value="contact" />

      <label>Name:</label>
      <input type="text" name="name" required />
        <br>
        <br>
      <label>Email:</label>
      <input type="email" name="email" required />
        <br>
        <br>
      <label>Message:</label>
      <textarea name="message" required></textarea>

      <button type="submit">Send</button>
    
    </form>
 
</template>
<style>
.form {
  border: 2px solid #5c4033; 
  background-color: #cfc8bf; 
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