<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  import addQuestions from './addQuestions.svelte';
  let login = false;
  let view = 'addQuestions'; // possible values: 'Login', 'QuizManager', 'addQuestions'

  // @ts-ignore
  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
    if (login) view = 'QuizManager';
  }

  function showaddQuestions() {
    view = 'addQuestions';
  }
</script>

<style>
/*LOG OUT BUTTON*/
.logout-button {
    font-family: 'Roboto', sans-serif;
    background-color: #ffca1b;  
    color: #333;
    padding: 2px 10px;
    cursor: pointer;
    border: none;
    width: 100%; 
    height: 100%;
  }
</style>

{#if view === 'addQuestions'}
  <!-- svelte-ignore component-name-lowercase -->
  <addQuestions />
{:else if view === 'login'}
  <Login on:loginEvent={setLogin} />
{:else}
  <QuizManager on:addQuestions={showaddQuestions} />
{/if}

  