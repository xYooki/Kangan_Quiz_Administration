<script>

  import { goto } from '$app/navigation';

  function openAddQuestions() {
    goto('/addQuestions');
  }

 let user= "Admin_01"
 function handleLogout() {
    user = null;  
 }

 async function fetchQuestions() {
    try {
      const response = await fetch("https://kanganquizapi1/users.azurewebsites.net/questions");
      if (response.ok) {
        questions = await response.json();
      } else {
        console.error("Failed to fetch questions");
      }
    } catch (error) {
      console.error("An error occurred:", error);
    }
  }
  import { onMount } from "svelte";
  onMount(fetchQuestions);

 
</script>

<button class="add-button" on:click={openAddQuestions}>Add Questions</button>

<style>
  /*HEADER*/  
  .manage-questions {
    font-family: 'Roboto', sans-serif;
    font-size: 40px;
    margin-bottom: 15px;
    margin-top: -50px;
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
    font-family: 'Roboto', sans-serif;
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
/*LOG OUT BUTTON*/
.logout-button {
    font-family: 'Roboto', sans-serif;
    background-color: #fff;
    color: #000;
    padding: 5px 10px;
    cursor: pointer;
    border: none;
    border-radius: 5px;
  }

/*QUESTIONS LIST CONTAINER*/
.container {
  background-color: #333; 
  color: white;
  padding: 100px;
  margin-top: -876px;
  margin-left: 200px;
  margin-right: 200px;
  height: 42.25em;
  width: 93em;
  display: flex;          /* Use Flexbox */
  flex-direction: column; /* Stack items vertically */
  align-items: flex-start; /* Align items to the start of the container */
}


  /*THE QUESTIONS CONTAINERS*/
  /* Style for the question containers */
.question-container {
  background-color: #535252; /* Light grey background */
  margin-bottom: 30px; /* Spacing between question containers */
  padding: 10px;
  width: 80em;
  height: 5em;
  border-radius:15px;
}

/* Style for question text */
.question-text {
  font-family: 'Roboto', sans-serif;
  font-size: 30px;
  margin-top: 16px;
  margin-bottom: -5px;
}

/* Style for DELETE and EDIT buttons */
.buttons {
  display: flex;
  margin-right: 10em;
}

/* Style for the delete and edit buttons */
.delete-button,
.edit-button {
  color: #fff; 
  border: none;
  padding: 90px;
  cursor: pointer;
  background: transparent; 
  margin-right: -93em;
  margin-left: 80em;
  margin-top: -3em;
}

.delete-button::before,
.edit-button::before {
  content: " | "; 
}


.delete-button:first-of-type::before,
.edit-button:first-of-type::before {
  content: ""; 
}

/* Add button styles */
.add-button {
  position: fixed;
  bottom: 40px;  
  right: 40px;  
}

.sticky-add-button {
  background-color: rgb(254, 254, 254);  
  color: #000000; 
  padding: 10px 20px; 
  border: none;  
  border-radius: 15px;  
  cursor: pointer;
  height: 3em;
  width: 8em;
  font-size: 25px;
  font-family: 'Roboto', sans-serif;
}

.sticky-add-button:hover {
  background-color: #000000;  
  color:#ffffff; 
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
  

  <!-- THE TEXT THAT TELLS YOU WHO YOURE LOGGED IN AS AND LOGS YOU OUT -->
<div class="bottom-bar">
  <span>ADMIN: {user}</span>
  <a href="http://localhost:5173">  
    <button class="logout-button" on:click={handleLogout}>LOG OUT</button>
  </a>
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
  <div class="manage-questions">
    <h>MANAGE QUESTIONS</h>
  </div>

  {#each questions as question, index (question.id)} <!-- Each question in the database SHOULD have a unique ID -->
    <div class="question-container">
      <div class="question-text">
        <!-- Display the question content here -->
        Q.{index + 1} {question.text}
      </div>
      <div class="buttons">
        <button class="delete-button">DELETE</button>
        <button class="edit-button">EDIT</button>
      </div>
    </div>
  {/each}

  <!-- Add new question button -->
  <div class="add-button">
    <button class="sticky-add-button">ADD</button>
  </div>
</div>
  
          <div class="add-button">
      <button class="sticky-add-button">ADD</button>
    </div>
  


 


 
  