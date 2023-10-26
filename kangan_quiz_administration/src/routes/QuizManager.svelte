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
    background-color: #333;
  }

  /*TOP BAR*/
  .top-bar {
    background-color: #ffca1b; 
    padding: 10px 20px;
    color: #333; /* Text color for top bar */
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 8em;
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
  display: flex;
  align-items: center;  
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.3s;
  font-family: 'Roboto', sans-serif;
  height: 2.5em;
  }

  /*FILLING THE SPACE UNDER THE TABS*/
  .additional-content {
  background-color: #000000; 
  color: white;
  flex: 1;  
  padding: 10px;  
  margin-top: 0px; /* Adjust margin-top to change the vertical position */
  margin-left: 00px; /* Adjust margin-left to change the horizontal position */
  margin-right: 200px;
  height:31em;
  width:180px;
  }


 .tab span {
  flex: 1;  
  }
  .tab:hover {
  background-color: #ffd102; /* Change the hover background color as desired */
  }

  /*QUESTIONS LIST CONTAINER*/
  .container {
  background-color: #333; 
  color: white;
  flex: 1;  
  padding: 100px;  
  margin-top: -876px; /* Adjust margin-top to change the vertical position */
  margin-left: 200px; /* Adjust margin-left to change the horizontal position */
  margin-right: 200px;
  height:42.25em;
  width:93em;
}

  /*LOG OUT BUTTON*/
  .logout-button {
    font-family: 'Roboto', sans-serif;
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
      <a href="https://www.kangan.edu.au/"> 
        <img src="Kangan_logo.png" alt="Kangan Logo" class="logo" />
      </a>
      <a href="https://youtu.be/oKqQCHNWP-o?si=Ub7fefgNyd2YAEah">  
        <img src="Tafe_Logo.png" alt="Tafe Vic Logo" class="logo" />
      </a>
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
    <div class="tab"><span>QUESTIONS</span></div>
    <div class="tab"><span>USERS</span></div>
    <div class="tab"><span>SETTINGS</span></div>
    <div class="tab"><span>TEST</span></div>
    <div class="tab"><span>TEST</span></div>
    <div class="tab"><span>TEST</span></div>
  </div>

 <!--this is a lowkey bad way to fill in the white space lmao-->
  <div class="additional-content"> </div>

   <!--QUESTIONS LIST CONTAINER-->
   <div class="container">
    </div>
  
 
  


 


 
  