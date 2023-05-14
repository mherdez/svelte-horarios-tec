<script>
    import CreateTable from './createTable.svelte';

    const numSemestres = [1,3,5,7,9]
    const turno = 'matutino'
    // const turno = 'vespertino'


</script>

<main>
  <nav class="navbar bg-dark text-light">
    <h1 class="mx-auto">Horarios</h1>
  </nav>
  <div class="container">
    <CreateTable {numSemestres} {turno} />
  </div>


</main>
