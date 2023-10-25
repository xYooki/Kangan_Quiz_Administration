<script>
  import { createEventDispatcher } from "svelte";

  let dispatch = createEventDispatcher();
  
   function loginHandler(status) {
    console.log(status);
    dispatch('loginEvent', {
      login: status
    });
  }

   import { onMount } from 'svelte';
   
// Load the Roboto font on component mount
onMount(() => {
  const link = document.createElement('link');
  link.href = 'https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap';
  link.rel = 'stylesheet';
  document.head.appendChild(link);
});
</script>

<style>
.loginHandler {
  background-color: #000; /* Black background */
  color: #fff; /* White text color */
  border: none;
  cursor: pointer;
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
    justify-content: center; /* Center the content horizontally */
    align-items: center; /* Center the content vertically */
    width: 50%; /* Set the width to 50% to fill the right half of the page */
    height: 100%;
    background-color: #ffd102; /* Background color with opacity */
    color: white;
  }

  /* Style for the "LOGIN" button */
  .loginHandler {
    background-color: #000;
    color: #fff;
    border: none;
    cursor: pointer;
    /* Adjust the margin-left as needed */
    margin-left: 70%;
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
    margin-right: 50%;
    display: block;  
    color: #000000;
  }

  .login-form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* Style for the input field */
  .input-field {
    margin-bottom: 10px;
  }

</style>

<img class="background-image" src="Kangan_Background.png" alt="Background Image" />

<div class="container">
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
        <input type="text" id="username" name="username" placeholder="Enter your username" />
      </div>
    </div>
  </div>
</div>
