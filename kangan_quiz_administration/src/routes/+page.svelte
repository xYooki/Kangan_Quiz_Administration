<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  import AddQuestions from './addQuestions.svelte';
  let login = false;
  let view = 'login'; // possible values: 'login', 'quizManager', 'addQuestions'

  // @ts-ignore
  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
    if (login) view = 'quizManager';
  }

  function showAddQuestions() {
    view = 'addQuestions';
  }
</script>

{#if view === 'addQuestions'}
  <AddQuestions />
{:else if view === 'login'}
  <Login on:loginEvent={setLogin} />
{:else}
  <QuizManager on:addQuestions={showAddQuestions} />
{/if}

  