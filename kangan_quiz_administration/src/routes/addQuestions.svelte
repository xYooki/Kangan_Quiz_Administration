<script>
    let question = "";
    let answerA = "";
    let answerB = "";
    let answerC = "";
    let answerD = "";
    let correctAnswer = "";
  
    function submitQuestion() {
      // Send the question, answers, and correct answer to API.
      console.log(question, answerA, answerB, answerC, answerD, correctAnswer);
    }
  </script>
  
  <div>
    <h2>Add Question</h2>
    <label for="question">Q:</label>
    <input type="text" id="question" bind:value={question} placeholder="Enter question description"/>
  
    <div>
      <label for="answerA">A</label>
      <input type="text" id="answerA" bind:value={answerA} placeholder="Enter text"/>
      <input type="radio" name="correct" value="A" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerB">B</label>
      <input type="text" id="answerB" bind:value={answerB} placeholder="Enter text"/>
      <input type="radio" name="correct" value="B" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerC">C</label>
      <input type="text" id="answerC" bind:value={answerC} placeholder="Enter text"/>
      <input type="radio" name="correct" value="C" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerD">D</label>
      <input type="text" id="answerD" bind:value={answerD} placeholder="Enter text"/>
      <input type="radio" name="correct" value="D" bind:group={correctAnswer} />
    </div>
  
    <button on:click={submitQuestion}>Submit</button>
  </div>

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

    div {
        display: flex;
        flex-direction: column;
        gap: 1rem; /* Space between child elements */
        width: 100%;
        max-width: 400px; /* Max width to ensure responsiveness */
        margin: 0 auto; /* Center the content horizontally */
        padding: 1rem;
        font-family: Arial, sans-serif;
        background-color: #f5f5f5; /* Background color from quizManager */
        border: 1px solid #e0e0e0; /* Border from quizManager */
        border-radius: 4px;
    }

    h2 {
        text-align: center;
        font-size: 1.5rem;
        margin-bottom: 1rem;
        color: #444; /* Text color from quizManager */
    }

    label {
        font-weight: bold;
        margin-right: 0.5rem;
        color: #555; /* Slightly lighter text color for labels */
    }

    input[type="text"] {
        width: 100%;
        padding: 0.5rem;
        margin-bottom: 0.5rem;
        border: 1px solid #ccc;
        border-radius: 4px;
    }

    input[type="radio"] {
        margin-left: 0.5rem;
    }

    button {
        padding: 0.5rem 1rem;
        background-color: #007BFF;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    button:hover {
        background-color: #0056b3;
    }

    button:active {
        background-color: #004399;
    }

</style>