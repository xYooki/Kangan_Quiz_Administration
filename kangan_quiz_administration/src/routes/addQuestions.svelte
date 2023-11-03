<script>
let user= "Admin_01"

function handleLogout() {
    // @ts-ignore
    user = null;  
}

let question = "";
let correctAnswerA = "";
let answerB = "";
let answerC = "";
let answerD = "";


async function submitQuestion() {
// Send data to the database

  try {
    const response = await fetch('https://kanganquizapi1/users.azurewebsites.net/questions', {
      method: 'POST',
      body: JSON.stringify({
        question, correctAnswerA, answerB, answerC, answerD
      }),
      headers: {
        'Content-Type': 'application/json'
      }
    });

    // Check if the response indicates success
    if (response.ok) {
      //Reset form values after successful submission
      question = '';
      correctAnswerA = '';
      answerB = '';
      answerC = '';
      answerD = '';
      // @ts-ignore
      alert('Question submitted successfully!');
    } else {
      console.error('Failed to submit the question.');
    }
  } catch (error) {
    console.error('There was an error:', error);
  }
}

</script>

<style>
/*html {
    62.5% of the default font-size of 16px is 10px. This makes 1rem = 10px 
}

body {
  font-size: 1.6rem;  Default font-size is 16px now 
}*/
html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden; /* Prevents horizontal scrolling */
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Roboto, sans-serif;
  color: #fff;
}

/* Responsive font sizes */
h2.add-questions {
  font-size: 2.4rem; /* Headings are 24px and scalable */
  
}

label {
  font-size: 1.4rem; /* Labels are now 14px and scalable */
}

input[type="text"], .logout-button, .questionSubmit {
  font-size: 1.6rem; /* Input text and buttons are 16px */
}

/*FLEX CONTAINER*/
.main-flex-container {
  display: flex;
  flex-direction: column;
  height: 100vh; /* full height of the viewport */
  width: 100%; /* full width of the viewport */
  overflow: hidden; /* prevents scrollbars if not necessary */
}

/*HEADER*/
.header {
  flex-shrink: 0; /* prevents shrinking when content is added*/
}

/*TOP BAR*/
.top-bar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 13vh;
  background-color: #ffca1b; 
  padding: 1vh 2vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 10;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/*LOGOS*/
.logos {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo1 {
  height: 14vh;
  width: auto;
}

.logo2 {
  height: 8vh;
  width: auto;
  margin-left: 2vw;
}

/*TOP BAR_02*/
.bottom-bar {
  position: fixed;
  top: 13vh;
  left: 0;
  width: 100%;
  height: 6vh; /* responsive height */
  background-color: #000;
  padding: 0 2vw; /* responsive padding */
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 10; /* ensures it's above other content */
}

/*LOG OUT BUTTON*/
.logout-button {
  background-color: #fff;
  color: #000;
  font-size: 1.5vh; /* responsive font size */
  padding: 1vh 2vw;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  margin-left: 2vw;
}

.bottom-bar-right {
  display: flex;
  align-items: center;
  margin-left: auto;
}

.content-container {
  display: flex;
  flex-grow: 1; /* takes up all available space */
  overflow: hidden; /* prevents scrollbars if not necessary */
  margin-top: 19vh;
}

/*SIDE BAR*/
.sidebar {
  background-color: #000;
  width: 18%;
  height: calc(100vh - 19vh); /* responsive height */
  position: sticky;
  top: 19vh;
  padding: 1.25rem 0rem;
  overflow-y: auto;
  z-index: 5;
}

/*TABS*/
.tab {
  align-items: center;
  padding: 2vh 2vw;
  cursor: pointer;
  transition: background-color 0.3s;
  height: 3em;
}

.tab span {
  flex: 1;
}
.tab:hover {
  background-color: #ffd102;
  border-radius: 4px; 
}

/*MAIN QUESTION CONTAINER*/
.mainQuestionContainer {
  flex-grow: 1;
  padding: 0.5rem 1.25rem;
  background-color: #444444;
  overflow-y: auto; /* adds scrollbar if content is too long */
}

.topLineQs, .bottomLineQs {
  display: flex;
  justify-content: space-between; /* This will space out the child elements evenly */
  margin-bottom: 1rem; /* Adds some space between the two lines */
}

.question-container {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}

label, .questionSubmit {
  font-size: 3vh;
  margin-right: 0.5rem;
}

input[type="text"] {
  flex-grow: 1; /* Allows input to take up as much space as possible */
  margin-left: 0.5rem; /* Adds space between label and input */
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.questionSubmit {
  padding: 0.5rem 1rem;
  background-color: #000;
  color: #fff;
  border: none;
  border-radius: 4px;  
  cursor: pointer;
  width: 8em;
  transition: background-color 0.3s;
}

.questionSubmit:hover {
  background-color: #fff;
  color: #000
}

.questionSubmit:active {
  background-color: #ffca1b;
}

*, *::before, *::after {
  box-sizing: border-box;
}
</style>


<div class="main-flex-container">
  <!--HEADER-->
  <div class="header">
    <!-- TOP BAR WITH LOGOS -->
    <div class="top-bar">
      <div class='logos'>
        <a href="https://www.kangan.edu.au/"> 
          <img src="Kangan_logo.png" alt="Kangan Logo" class="logo1" />
        </a>
        <a href="https://youtu.be/oKqQCHNWP-o?si=Ub7fefgNyd2YAEah">  
          <img src="Tafe_Logo.png" alt="Tafe Vic Logo" class="logo2" />
        </a>
      </div>
    </div>

    <!-- USERNAME AND LOGOUT BUTTON -->
    <div class="bottom-bar">
      <div class="bottom-bar-right">
        <span class="user-info">ADMIN: {user}</span>
        <a href="http://localhost:5173">
          <button class="logout-button" on:click={handleLogout}>LOG OUT</button>
        </a>
      </div>
    </div>
  </div>

  <div class="content-container">
<!-- SIDEBAR AND TABS -->
    <div class="sidebar">
      <div class="tab"><span>QUESTIONS</span></div>
      <div class="tab"><span>USERS</span></div>
      <div class="tab"><span>SETTINGS</span></div>
      <div class="tab"><span>TEST</span></div>
      <div class="tab"><span>TEST</span></div>
      <div class="tab"><span>TEST</span></div>
    </div>
<!-- QUESTION CONTAINER -->
    <div class="mainQuestionContainer">

      <h2 class="add-questions">Add Questions</h2>
  
      <div class="question-container">
        <label for="questionNumber">{question}</label>
        <input type="text" id="questionNumber" bind:value={question} placeholder="Enter new question"/>
      </div>
      <div class="topLineQs">
        <div class="question-container">
          <label for="correctAnswerA">A)</label>
          <input type="text" id="correctAnswerA" bind:value={correctAnswerA} placeholder="Enter correct answer here"/>
        </div>

        <div class="question-container">
          <label for="answerB">B)</label>
          <input type="text" id="answerB" bind:value={answerB} placeholder="Enter text"/>
        </div>
      </div>

      <div class="bottomLineQs">
        <div class="question-container">
          <label for="answerC">C)</label>
          <input type="text" id="answerC" bind:value={answerC} placeholder="Enter text"/>
        </div>

        <div class="question-container">
          <label for="answerD">D)</label>
          <input type="text" id="answerD" bind:value={answerD} placeholder="Enter text"/>
        </div>
      </div>

      <button class=questionSubmit on:click={submitQuestion}>Submit</button>
    </div>

  </div>
</div>