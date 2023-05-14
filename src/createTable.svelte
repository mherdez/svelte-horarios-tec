<script>
  import { reticula } from './getData';
  export let numSemestres, turno;

  const totalMaterias = (numero) => reticula.filter((semestre) => semestre.semestre == numero);

</script>

{#each numSemestres as semestre}
    <h3 class="my-4 text-center ">Semestre {semestre}</h3>
    <table class="table table-striped">
      <thead>
        <tr class="table-success">
          <th>Asignatura</th>
          <th>Clave</th>
          <th>Créditos</th>
          <th>Lunes</th>
          <th>Martes</th>
          <th>Miércoles</th>
          <th>Jueves</th>
          <th>Viernes</th>
          <th>Docente</th>
        </tr>
      </thead>
      <tbody>
        {#each totalMaterias(semestre) as materia}
          {#if materia.turno.includes(turno.slice(0,3)) || materia.turno.includes('mix')}
            <tr>
              <td id="asignatura">{materia.asignatura}</td>
              <td id="clave">{materia.clave.toUpperCase()}</td>
              <td id="créditos">
                {materia.horasTeoricas}-
                {materia.horasPracticas}-
                {materia.horasPracticas + materia.horasTeoricas}
              </td>
              <td id="lunes" />
              <td id="martes" />
              <td id="miercoles" />
              <td id="jueves" />
              <td id="viernes" />
              <td id="docente" class="table-warning" />
            </tr>
          {/if}
        {/each}
      </tbody>
    </table>
{/each}
