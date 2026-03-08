<template>
  <div class="container">

    <nav class="navbar">
      <a href="/">Home</a>
      <a href="/projects">Projects</a>
      <a href="/contact">Contact</a>
    </nav>

    <NuxtPage />

  </div>
</template>

<style>

/* Page background */
body{
  background-color: #f0ece9; 
  font-family: Arial, Helvetica, sans-serif;
  margin: 0;
  color: #3b2a1f; 
}


/* Navbar */
.navbar{
  display: flex;
  justify-content: center; 
  gap: 40px;
  background-color: #5a3e2b;
  padding: 15px;
  border-radius: 10px;
  margin-bottom: 40px;
}

/* Navbar links */
.navbar a{
  text-decoration: none;
  color: #f5e6d3;
  font-size: 18px;
  font-weight: bold;
  transition: 0.3s;
}

/* Hover effect */
.navbar a:hover{
  color: #3b2a1f;
  background-color: #f0ece9; 
  padding: 8px 15px;
  border-radius: 5px;
}
/* footer */
footer {
  background-color: #eee7e2;
  color: #241c0f;
  text-align: center;
  width: 100%;
  padding: 16px;
  font-weight: 300;
  font-size: 0.9rem;
  border-radius: 10px;
  margin: 20px;
}

</style>