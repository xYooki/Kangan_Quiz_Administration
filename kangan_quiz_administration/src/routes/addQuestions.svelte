<script>

export let username;

function handleLogout() {
    // @ts-ignore
    username = null;  
}

let question = "";
let correctOption1 = "";
let option2 = "";
let option3 = "";
let option4 = "";


async function submitQuestion() {
// Send data to the database

  try {
    const response = await fetch('https://kanganquizapi1/users.azurewebsites.net/questions', {
      method: 'POST',
      body: JSON.stringify({
        question, correctOption1, option2, option3, option4
      }),
      headers: {
        'Content-Type': 'application/json'
      }
    });

    // Check if the response indicates success
    if (response.ok) {
      //Reset form values after successful submission
      question = '';
      correctOption1 = '';
      option2 = '';
      option3 = '';
      option4 = '';
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

/* CSS RESET */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Roboto, sans-serif;
  color: #fff;
}

/* Responsive font sizes */
h2.add-questions {
  font-size: 2rem; /* Headings are 24px and scalable */
  margin: 2rem 0rem;
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
  padding: 0.5vh 2vw; /* responsive padding */
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
  border-radius: 0.5dvw;
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
  border-radius: 1vw; 
}

/*MAIN QUESTION CONTAINER*/
.mainQuestionContainer {
  flex-grow: 1;
  padding: 0.5rem 1.25rem;
  background-color: gray;
  overflow-y: auto; /* adds scrollbar if content is too long */
}

.question-container {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin-bottom: 1rem;
  margin-right: 2rem;
}

.topLineQs, .bottomLineQs {
  display: flex;
  justify-content: flex-start; /* This will space out the child elements evenly */
}

.topLineQs .question-container, .bottomLineQs .question-container{
  flex: 1; /* Give equal space to containers */
  display: flex;
  justify-content: space-between; /* Label left and the input right */
  margin-right: 0.5rem; /* Adjust the right margin to match the gap between containers */
}

.topLineQs .question-container:last-child, .bottomLineQs .question-container:last-child {
  margin-right: 2rem; /* Reduce right margin for the last containers */
  margin-left: 0; 
}



.topLineQs input[type="text"],
.bottomLineQs input[type="text"] {
  flex-grow: 1; /* Let the input grow to fill the container */
  /* Do not set a fixed width here; let flexbox handle it */
}

.question-container label {
  white-space: nowrap; /* Prevents the label from wrapping and ensures it stays on one line */
  margin-right: 0.5rem; /* Space between label and input */
}

#newQuestion {
  display: flex;
  justify-content: space-between; /* Label to the left, input to the right */
  align-items: center;
}

#newQuestion input[type="text"] {
  flex-grow: 1;
}


label {
  font-size: 3vh;
  text-align: right;
  margin-right: 0.5rem;
  min-width: 7em;
  white-space: nowrap; /* Prevents label text from wrapping */
}

input[type="text"] {
  flex-grow: 1; /* Allows input to take up as much space as possible */
  margin-left: 0.5rem; /* Adds space between label and input */
  min-width: none;
  padding: 0.75rem;
  margin-bottom: 0.5rem;
  border: none;
  border-radius: 2vw;
  color: #000;
  background-color: dimgray;
}

.questionSubmit {
  display: flex;
  justify-content: center;
  padding: 0.5rem 1rem;
  background-color: lightgray;
  color:dimgray;
  border: none;
  border-radius: 1.75vw;
  cursor: pointer;
  width: 6em;
  transition: background-color 0.3s;
  margin-left: auto;
  margin-right: 2rem;
  margin-bottom: 0.5rem;
}

.questionSubmit:hover {
  background-color: #ffca1b;
  color: #fff;
}

.questionSubmit:active {
  background-color: #000;
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
        <span class="user-info">ADMIN: {username}</span>
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

      <h2 class="add-questions">ADD QUESTIONS</h2>
  
      <div class="question-container" id="newQuestion">
        <label for="questionNumber">New Question</label>
        <input type="text" id="questionNumber" bind:value={question} placeholder="Enter new question"/>
      </div>

      <div class="topLineQs">
        <div class="question-container">
          <label for="correctOption1">A)</label>
          <input type="text" id="correctOption1" bind:value={correctOption1} placeholder="Enter correct answer here"/>
        </div>

        <div class="question-container">
          <label for="option2">B)</label>
          <input type="text" id="option2" bind:value={option2} placeholder="Enter text"/>
        </div>
      </div>

      <div class="bottomLineQs">
        <div class="question-container">
          <label for="option3">C)</label>
          <input type="text" id="option3" bind:value={option3} placeholder="Enter text"/>
        </div>

        <div class="question-container">
          <label for="option4">D)</label>
          <input type="text" id="option4" bind:value={option4} placeholder="Enter text"/>
        </div>
      </div>

      <button class=questionSubmit on:click={submitQuestion}>SUBMIT</button>
    </div>
  </div>
</div>