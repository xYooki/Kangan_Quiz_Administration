<script>
 let user= "ur mum"
</script>

<style>
    /*MAIN PAGE BACKGROUND*/
    body {
    background-color: #333;
  }

  /*CONTAINER WITH A SCROLL BAR*/
  .questions-container {
    overflow-y: scroll;
    max-height: 400px; /* Adjust the maximum height as needed */
  }
    /*TOP BAR*/
    .top-bar {
    background-color: #ffd102;
    padding: 10px 20px;
    color: #333; /* Text color for top bar */
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 10em;
    width: auto;
  }

    /*TOP BAR_02*/
    .bottom-bar {
    background-color: #000;
    color: #fff;
    padding: 10px 20px;
    text-align: right;
  }
  
    /*LOGO SPACE*/
    .logo {
      margin-right: 10px;
      height: 6em;
      width: auto;
    }

    /*SIDE BAR*/
    .sidebar {
    background-color: #000;
    color: #fff;
    width: 200px; /* Adjust the width as needed */
  }

    /*TABS*/
    .tab {
    padding: 10px;
    cursor: pointer;
    transition: background-color 0.3s;
    font-family: 'Roboto', sans-serif;
  }
    .tab:hover {
    background-color: #ffd102; /* Change the hover background color as desired */
  }

  /*LOG OUT BUTTON*/
  .logout-button {
    background-color: #fff;
    color: #000;
    padding: 5px 10px;
    cursor: pointer;
    border: none;
  }




  </style>
  
  <!-- LOGO MANAGEMENT -->
  <div class="top-bar">
    <div>
        <img src="Kangan_logo.png" alt="Kangan Logo" class="logo" />
        <img src="Tafe_Logo.png" alt="Tafe Vic Logo" class="logo" />
    </div>
</div>

  <!-- THE TEXT THAT TELLS YOU WHO YOURE LOGGED IN AS -->
  <div class="bottom-bar">
    <span>
      ADMIN: {user}  
    </span>
    <button class="logout-button" on:click={handleLogout}>LOG OUT</button>
  </div>

  <!-- FOR THE TABS -->
  <div class="sidebar">
    <div class="tab">QUESTIONS</div>
    <div class="tab">USERS</div>
    <div class="tab">SETTINGS</div>
   </div>


 


 
  