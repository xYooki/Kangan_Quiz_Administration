<script>
  import { createEventDispatcher } from "svelte";
  import { onMount } from 'svelte';

  let dispatch = createEventDispatcher();
  let username = "";
  let loginStatus = "";

  // Load the Roboto font on component mount
  onMount(() => {
    const link = document.createElement('link');
    link.href = 'https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap';
    link.rel = 'stylesheet';
    document.head.appendChild(link);
  });

  async function loginHandler(username) {
  try {
    console.log(`https://kanganquizapi1.azurewebsites.net/users/${username}`);
    const response = await fetch(`https://kanganquizapi1.azurewebsites.net/users/${username}`, {
      method: 'GET',
      mode: 'no-cors'
    });

    if (response.ok) {
      const data = await response.json();
      if (data === true) { 
        goto('quizmanager');
      } else {
        loginStatus = "Login failed";
      }
    } else {
      loginStatus = "Login failed";
    }
  } catch (error) {
    console.error("An error occurred:", error);
    loginStatus = "An error occurred";
  }
}



</script>

 
<style>
  html, body {
  margin: 0;
  padding: 0;
  background-color: #333;
}

  /* Style for the background image covering the page */
  .background-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%; /* Set the width to 100% to cover the entire page */
    height: 100%;
    z-index: -1;
  }

  /* Style for the container, centering, and form */
  .container {
    display: flex;
    justify-content: space-between; /* Align content to the left and right */
    height: 100vh;
  }

  .left-content {
    display: flex;
    flex-direction: column;
    justify-content: center; 
    align-items: center;
  }

  .right-content {
    display: flex;
    flex-direction: column;
    justify-content: center; 
    align-items: center;  
    width: 50%;  
    height: 100%;
    background-color: #ffca1b;  
    color: white;
    margin-top: -1em
  }

  /* Style for the "LOGIN" button */
  .loginHandler {
    font-family: 'Roboto', sans-serif;
    background-color: #000;
    color: #fff;
    border: none;
    cursor: pointer;
    margin-left: 62%;
    border-radius: 10px; 
    height: 3em;
    width: 10em;
    font-size:15px;
  }

  .logo {
    margin-right: -90%; 
    width: 500px;  
    height: auto;
  }

  .username-label {
    font-family: 'Roboto', sans-serif;
    text-transform: uppercase;
    margin-bottom: 10px;  
    margin-right: 65%;
    display: block;  
    color: #000000;
    font-size: 1.5em; 
  }

  .login-form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* Style for the input field */
  .input-field {
    margin-bottom: 10px;
    font-size:5;
  }

  /* Style for the rounded input box with no borders */
.rounded-input {
  border: none;  
  border-radius: 10px;  
  padding: 10px;  
  background-color: #f2f2f2; 
  width: 30em;
  height: 4em;
}


</style>

<img class="background-image" src="Kangan_Background.png" alt="Background Image" />

<div class="container">0
  <div class="left-content">
    <img class="logo" src="White_Kangan_Logo.png" alt="Logo" />
    <!-- Your background image content -->
  </div>

  <div class="right-content">
    <div class="logo-container">
    </div>

    <div class="login-form-container">
      <label class="username-label" for="username">USERNAME:</label>
      <div class="input-field">
        <input type="text" id="username" name="username" placeholder="Enter your username" class="rounded-input">
      </div>
  <button class="loginHandler" on:click={() => loginHandler(document.getElementById('username').value)}>LOG IN</button>
  </div>
  </div>
</div>
