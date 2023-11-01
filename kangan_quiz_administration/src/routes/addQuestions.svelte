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
      <label for="answerA">A)</label>
      <input type="text" id="answerA" bind:value={answerA} placeholder="Enter text"/>
      <input type="radio" name="correct" value="A" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerB">B)</label>
      <input type="text" id="answerB" bind:value={answerB} placeholder="Enter text"/>
      <input type="radio" name="correct" value="B" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerC">C)</label>
      <input type="text" id="answerC" bind:value={answerC} placeholder="Enter text"/>
      <input type="radio" name="correct" value="C" bind:group={correctAnswer} />
    </div>
  
    <div>
      <label for="answerD">D)</label>
      <input type="text" id="answerD" bind:value={answerD} placeholder="Enter text"/>
      <input type="radio" name="correct" value="D" bind:group={correctAnswer} />
    </div>
  
    <button on:click={submitQuestion}>Submit</button>
  </div>

<style>
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