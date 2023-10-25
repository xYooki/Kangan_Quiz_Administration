<script>
    import { Router, Link } from "svelte-routing";
    import Login from "./Login.svelte";
    import QuizManager from "./QuizManager.svelte";
  </script>
  
  <Router>
    <Login path="/" />
    <QuizManager path="/quiz-manager" />
  </Router>