## Question 001

### **Q1: Which statement is correct regarding passing permissions to reusable workflows?**

- The `GITHUB_TOKEN` permissions passed from the caller workflow can be only downgraded by the called workflow.

### **P1: ¿Cuál afirmación es correcta con respecto a otorgar permisos a flujos de trabajo reutilizables?**

- Los `GITHUB_TOKEN`permisos transferidos desde el flujo de trabajo que llama solo pueden ser reducidos por el flujo de trabajo llamado.

### Recurso de estudio

[Reusing workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/reusing-workflows#access-and-permissions)

## Question 002

### **Q2: What are the different permission levels you can assign to `GITHUB_TOKEN` in the `permissions` block?**

- none, write, read

### **P2: ¿Cuáles son los diferentes niveles de permiso que puedes asignar `GITHUB_TOKEN`en el `permissions`bloque?**

- ninguno, escribir, leer

### Recurso de estudio

[Controlling permissions for GITHUB_TOKEN - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/controlling-permissions-for-github_token)

## Question 003

### **Q3: You can use `permissions` to modify the `GITHUB_TOKEN` permissions on: (Select two.)**

- Job level
- Workflow level

### **P3: Puede utilizar `permissions`para modificar los `GITHUB_TOKEN`permisos en: (Seleccione dos).**

- Nivel de trabajo
- Nivel de flujo de trabajo

### Recurso de estudio

[Controlling permissions for GITHUB_TOKEN - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/controlling-permissions-for-github_token)

## Question 004

### **Q4: Are GitHub Actions free for public repositories?**

- Yes

### **P4: ¿Las GitHub Actions son gratuitas para los repositorios públicos?**

- si

## Question 005

### **Q5: Which of these is not a valid event that could trigger a workflow?**

- Cloning the repository

### **P5: ¿Cuál de estos no es un evento válido que podría desencadenar un flujo de trabajo?**

- Clonando el repositorio

### recursos de estudio

[Events that trigger workflows - GitHub Docs](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#about-events-that-trigger-workflows)

## Question 006

### **Q6: Which is true about workflows? (Select three.)**

- Workflows have to be defined in the `.github/workflows` directory
- Workflows can be triggered manually, by an event or run on a schedule
- Workflows can run one or multiple jobs at a time

### **P6: ¿Cuál de estas afirmaciones es verdadera sobre los flujos de trabajo? (Seleccione tres).**

- Los flujos de trabajo deben definirse en el `.github/workflows`directorio
- Los flujos de trabajo se pueden activar manualmente, mediante un evento o ejecutarse según un cronograma.
- Los flujos de trabajo pueden ejecutar uno o varios trabajos a la vez

### Recurso de estudio

[About workflows - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-workflows)

## Question 007

### **Q7: Which components are required for a workflow? (Select two.)**

- One or more events that will trigger the workflow
- One or more jobs

### **P7: ¿Qué componentes se requieren para un flujo de trabajo? (Seleccione dos).**

- Uno o más eventos que activarán el flujo de trabajo
- Uno o más trabajos

### Recurso de estudio

[Acerca de los flujos de trabajo - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-workflows#workflow-basics)

## Question 008

### **Q1: Which event is triggered by a webhook action from outside of the repository?**

- repository_dispatch

### **P 1 : ¿Qué evento se activa mediante una acción de webhook desde fuera del repositorio?**

- envío del repositorio

### Recurso de estudio

[Events that trigger workflows - Documentación de GitHub](https://docs.github.com/es/actions/reference/events-that-trigger-workflows)

## Question 009

### **Q9: Workflows are defined in which format**

- yaml - yml

### **P9: ¿En qué formato se definen los flujos de trabajo?**

- yaml - yml

## Question 010

### **Q10: Where should you store sensitive data such as passwords or certificates that will be used in workflows**

- Secerts

### **P10: ¿Dónde debe almacenar datos confidenciales, como contraseñas o certificados, que se utilizarán en los flujos de trabajo?**

- Secretos

## Question 011

### **Q11: In a workflow with multiple jobs the default behavior is:**

- All jobs run in parallel

### **P11: En un flujo de trabajo con múltiples trabajos, el comportamiento predeterminado es:**

- Todos los trabajos se ejecutan en paralelo

### Recurso de estudio

[Acerca de los flujos de trabajo - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-workflows#creating-dependent-jobs)

## Question 012

### **Q12: If job B requires job A to be finished you have to:**

- use the `needs` keyword in job B to create this dependency

### **P12: Si el trabajo B requiere que se termine el trabajo A, usted debe:**

- Utilice la `needs`palabra clave en el trabajo B para crear esta dependencia

### Recurso de estudio

[Acerca de los flujos de trabajo - Documentación de GitHub](http://docs.github.com/es/actions/concepts/workflows-and-actions/about-workflows#creating-dependent-jobs)

## Question 013

### **Q13: In a workflow with multiple jobs, if job A fails then:**

- the jobs that are dependent on job A are skipped

### **P13: En un flujo de trabajo con varios trabajos, si el trabajo A falla, entonces:**

- Los trabajos que dependen del trabajo A se omiten

### Recurso de estudio

[Acerca de los flujos de trabajo - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-workflows#creating-dependent-jobs)

## Question 014

### Q14: This code will launch 6 different jobs in parallel using the matrix strategy. Can you use the matrix strategy to parallelize entire workflows?

```yaml
jobs:
  example_matrix:
    strategy:
      matrix:
        version: [10, 12, 14]
        os: [ubuntu-latest, windows-latest]
```

- Yes

### P14: Este código ejecutará seis trabajos diferentes en paralelo utilizando la estrategia matricial. ¿Se puede usar la estrategia matricial para paralelizar flujos de trabajo completos?

```yaml
jobs:
  example_matrix:
    strategy:
      matrix:
        version: [10, 12, 14]
        os: [ubuntu-latest, windows-latest]
```

- Si

### Recurso de estudio

[Reusing workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/reusing-workflows#using-a-matrix-strategy-with-a-reusable-workflow)

## Question 015

### **Q15: Which matrix job definition is syntactically correct?**

```yaml
jobs:
	example_matrix:
		strategy:
			matrix:
				version: [10, 12, 14]
				os: [ubuntu-latest, windows-latest]
```

### **P15: ¿Qué definición de trabajo matricial es sintácticamente correcta?**

```yaml
jobs:
	example_matrix:
		strategy:
			matrix:
				version: [10, 12, 14]
				os: [ubuntu-latest, windows-latest]
```

### Recurso de estudio

[Running variations of jobs in a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow#using-a-matrix-strategy)

## Question 016

### **Q16: How do you access matrix variables in a matrix strategy job?**

- Using the `matrix` context

### **P16: ¿Cómo se accede a las variables de matriz en un trabajo de estrategia matricial?**

- Usando el `matrix`contexto

### Recurso de estudio

[Running variations of jobs in a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow#using-a-matrix-strategy)

## Question 017

### **Q17: When using the `pull_request` and `pull_request_target` events, how do you configure the workflow to run only when targeting the `prod` branch?**

- Using `branches` filter

### **P17: Al utilizar los eventos `pull_request`y `pull_request_target`, ¿cómo se configura el flujo de trabajo para que se ejecute solo cuando se apunta a la `prod`rama?**

- Usando `branches`filtro

### Recurso de estudio

[Triggering a workflow - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-when-your-workflow-runs/triggering-a-workflow#using-filters-to-target-specific-branches-for-pull-request-events)

## Question 018

### Q18: This workflow will run on all pull requests where:

```yaml
on:
  pull_request:
    branches:
      - 'release/**'
      - '!release/**-alpha'
```

- the target branch name starts with `release` but does not end with `-alpha`

### P18: Este flujo de trabajo se ejecutará en todas las solicitudes de extracción donde:

```yaml
on:
  pull_request:
    branches:
      - 'release/**'
      - '!release/**-alpha'
```

- El nombre de la rama de destino comienza con `release`pero no termina con`-alpha`

### Recurso de estudio

[Triggering a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-when-your-workflow-runs/triggering-a-workflow#example-including-and-excluding-branches)

## Question 019

### **Q19: Fill in the blank: When using `push` event trigger filters you can use <____> patterns to target multiple branches**

- glob

### **P19: Complete el espacio en blanco: Al usar `push`filtros de activación de eventos, puede usar patrones <____> para apuntar a múltiples ramas**

- globo

### Recurso de estudio

[Triggering a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-when-your-workflow-runs/triggering-a-workflow#using-filters-to-target-specific-branches-or-tags-for-push-events)

## Question 020

### Q20: Which event allows you to manually trigger a workflow from the GitHub UI?

- workflow_dispatch

### **P20: ¿Qué evento le permite activar manualmente un flujo de trabajo desde la interfaz de usuario de GitHub?**

- flujo de trabajo_despacho

### Recurso de estudio

[Manually running a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/manually-running-a-workflow)

## Question 021

### **Q21: What are the possible types of an input variable for a manually triggered workflow? (Select five.)**

- string
- number
- environment
- boolean
- choice

### **P21: ¿Cuáles son los posibles tipos de variables de entrada para un flujo de trabajo activado manualmente? (Seleccione cinco).**

- cadena
- numero
- ambiente
- booleano
- eleccion

### Recurso de estudio

[Workflow syntax for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#onworkflow_dispatchinputsinput_idtype)

## Question 022

### **Q22: A workflow that has only `workflow_dispatch` event trigger can be triggered using GitHub's REST API**

- True

### **P22: Un flujo de trabajo que solo tiene `workflow_dispatch`un activador de eventos se puede activar mediante la API REST de GitHub**

- verdadero

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#onworkflow_dispatchinputs)

## Question 023

### **Q23: To stop a workflow from running temporarily without modifying the source code you should**

- Use the `Disable workflow` option in GitHub Actions

### **P23: Para detener la ejecución de un flujo de trabajo temporalmente sin modificar el código fuente, debe**

- Utilice la `Disable workflow`opción en GitHub Actions

### Recurso de estudio

[Disabling and enabling a workflow - GitHub Docs](https://docs.github.com/en/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/disabling-and-enabling-a-workflow)

## Question 024

### **Q24: What are `activity types` of an event used for ?**

- Limiting workflow runs to specific activity types using the `types` filter

### **P24: ¿Para qué `activity types`se utiliza un evento?**

- Limitar las ejecuciones del flujo de trabajo a tipos de actividades específicos mediante el `types`filtro

### Recurso de estudio

[Events that trigger workflows - Documentación de GitHub](https://docs.github.com/es/actions/reference/events-that-trigger-workflows#about-events-that-trigger-workflows)

## Question 025

### **Q25: You want to create a reusable workflow `CI` that runs some quality checks, linting and tests on code changes. What event trigger should the `CI` workflow define to allow reusing it in other workflows?**

- workflow_call

### **P25: Desea crear un flujo de trabajo reutilizable `CI`que ejecute comprobaciones de calidad, análisis de errores y pruebas de cambios en el código. ¿Qué activador de evento debería `CI`definir el flujo de trabajo para permitir su reutilización en otros flujos de trabajo?**

- llamada_de_flujo_de_trabajo

### Recurso de estudio

[Events that trigger workflows - Documentación de GitHub](https://docs.github.com/es/actions/reference/events-that-trigger-workflows)

## Question 026

### **Q26: A reusable workflow named `build` creates zip file artifacts. How do you pass the zip file location to the caller workflow that is calling the `build` workflow? (Select three.)**

- You define an output on workflow level in the `build` workflow
- You define an output on job level in the `build` workflow
- In the `build` workflow you write the output into `$GITHUB_OUTPUT` in one of the steps

### **P26: Un flujo de trabajo reutilizable llamado `build`crea artefactos de archivos zip. ¿Cómo se pasa la ubicación del archivo zip al flujo de trabajo que lo llama `build`? (Seleccione tres opciones).**

- Define una salida a nivel de flujo de trabajo en el `build`flujo de trabajo
- Define una salida a nivel de trabajo en el `build`flujo de trabajo
- En el `build`flujo de trabajo, escribe la salida `$GITHUB_OUTPUT`en uno de los pasos

### Recurso de estudio

[Reusing workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/reusing-workflows#using-outputs-from-a-reusable-workflow)

## Question 027

### **Q27: What are the valid use cases for using defaults? (Select two.)**

- Using defaults.run on job level to set default working-directory for all steps in a single job
- Using defaults.run on workflow level to set default shell (e.g bash) for an entire workflow

### **P27: ¿Cuáles son los casos de uso válidos para utilizar valores predeterminados ? (Seleccione dos).**

- Uso de defaults.run en el nivel de trabajo para establecer el directorio de trabajo predeterminado para todos los pasos en un solo trabajo
- Usar defaults.run en el nivel de flujo de trabajo para establecer el shell predeterminado (por ejemplo, bash) para un flujo de trabajo completo

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#defaults)

## Question 028

### **Q28: How can you ensure that a workflow called `Deploy Prod` is always running at most one at a time?**

```yaml
# Use concurrency on workflow level
	concurrency: ${{ github.workflow }}
```

### **P28: ¿Cómo se puede garantizar que un flujo de trabajo llamado `Deploy Prod`se esté ejecutando siempre como máximo una vez?**

```yaml
# Uso concurrencyen el nivel de flujo de trabajo
concurrency: ${{ github.workflow }}
```

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#concurrency)

## Question 029

### **Q29: Your Pull Request analysis workflow uses multiple code analysis tools and takes about 20 minutes to fully complete. It is triggered on `pull_request` event with `branches` filter set to `master`. Therefore if a developer pushes multiple commits within few minutes multiple workflows are running in parallel. How can you stop all previous workflow runs and only run the one with latest changes?**

```yaml
# Use concurrency with cancel-in-progress
concurrency:
 group: ${{ github.workflow }}-${{ github.ref }}
 cancel-in-progress: true
```

### **P29: El flujo de trabajo de análisis de solicitudes de incorporación de cambios utiliza varias herramientas de análisis de código y tarda unos 20 minutos en completarse. Se activa en `pull_request`un evento con `branches`el filtro establecido en `master`. Por lo tanto, si un desarrollador envía varias confirmaciones en pocos minutos, varios flujos de trabajo se ejecutan en paralelo. ¿Cómo se pueden detener todas las ejecuciones anteriores del flujo de trabajo y ejecutar solo la que contiene los cambios más recientes?**

```yaml
# Utilice concurrencia con cancelación en progreso
concurrency:
 group: ${{ github.workflow }}-${{ github.ref }}
 cancel-in-progress: true
```

### Recurso de estudio

[Workflow syntax for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#example-using-concurrency-to-cancel-any-in-progress-job-or-run)

## Question 030

### **Q30: When will job3 run?**

```yaml
  jobs:
    job1:
    job2:
      needs: job1
    job3:
      if: ${{ always() }}
      needs: [job1, job2]
```

- job3 will run after job1 and job2 have completed, regardless of whether they were successful

### P30: ¿Cuándo se ejecutará el trabajo 3?

```yaml
  jobs:
    job1:
    job2:
      needs: job1
    job3:
      if: ${{ always() }}
      needs: [job1, job2]
```

- job3 se ejecutará después de que job1 y job2 se hayan completado, independientemente de si tuvieron éxito o no.

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#example-not-requiring-successful-dependent-jobs)

## Question 031

### **Q31: What `jobs.job_id.if` conditional will make sure that job `production-deploy` is triggered only on `my-org/my-repo` repository? (Select two.)**

```yaml
jobs:
    production-deploy:
      if: <CONDITION>
      runs-on: ubuntu-latest
      steps:
        ...
```

- if: github.repository == 'my-org/my-repo’
- if: ${{ github.repository == 'my-org/my-repo' }}

### **P31: ¿Qué `jobs.job_id.if`condición garantizará que el trabajo `production-deploy`se active solo en `my-org/my-repo`el repositorio? (Seleccione dos).**

```yaml
jobs:
    production-deploy:
      if: <CONDITION>
      runs-on: ubuntu-latest
      steps:
        ...
```

- if: github.repository == 'my-org/my-repo’
- if: ${{ github.repository == 'my-org/my-repo' }}

### Recurso de estudio

[Acceso a información contextual sobre ejecuciones de flujo de trabajo - Documentación de GitHub](https://docs.github.com/es/actions/reference/accessing-contextual-information-about-workflow-runs#github-context)

## Question 032

### **Q32: What GitHub-hosted runner types are available to use? (Select three.)**

- macOS
- Windows
- Ubuntu Linux

### **P32: ¿Qué tipos de ejecutores alojados en GitHub están disponibles para usar? (Seleccione tres).**

- macOS
- Windows
- Ubuntu Linux

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#choosing-github-hosted-runners)

## Question 033

### **Q33: Is this statement true? `Not all steps run actions, but all actions run as a step`**

- true

### **P33: ¿Es verdadera esta afirmación?`Not all steps run actions, but all actions run as a step`**

- verdadero

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idsteps)

## Question 034

### **Q34: For any action published in GitHub Marketplace, you can often use it in multiple versions, which approach is the most stable and secure?**

- Reference the commit SHA

### **P34: Para cualquier acción publicada en GitHub Marketplace, a menudo puedes usarla en múltiples versiones, ¿qué enfoque es el más estable y seguro?**

- Hacer referencia al SHA de confirmación

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](http://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#example-using-versioned-actions)

## Question 035

### **Q35: To prevent a job from failure when one of the steps fails you can include:**

```yaml
# continue-on-error flag in the failing step
 steps:
   - uses: my-org/failing-action@v1
     continue-on-error: true
```

### **P35: Para evitar que un trabajo falle cuando uno de los pasos falla, puede incluir:**

- 1

```yaml
# continue-on-error bandera en el paso fallido
steps:
   - uses: my-org/failing-action@v1
     continue-on-error: true
```

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepscontinue-on-error)

## Question 036

### **Q36: You defined a matrix job `example_matrix`. How can limit the matrix to run a maximum of 2 jobs at a time?**

```yaml
  jobs:
    example_matrix:
      strategy:
        matrix:
          version: [10, 12, 14]
          os: [ubuntu-latest, windows-latest]
```

- Set `jobs.example_matrix.strategy.max-parallel` to 2

### P36: Definió un trabajo de matriz `example_matrix`. ¿Cómo puedo limitar la matriz para que ejecute un máximo de dos trabajos a la vez?

```yaml
  jobs:
    example_matrix:
	    # agreggamos
	    max-parallel: 2
      strategy:
        matrix:
          version: [10, 12, 14]
          os: [ubuntu-latest, windows-latest]
```

- Establecer `jobs.example_matrix.strategy.max-parallel`en 2

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstrategymax-parallel)

## Question 037

### **Q37: Which of these is a proper way of setting an output parameter `PET` with a value of `DOG` in a `step`.**

- echo "PET=DOG" >> "$GITHUB_OUTPUT”

### **P37: ¿Cuál de estas es una forma adecuada de configurar un parámetro de salida `PET`con un valor de `DOG`en un `step`.**

- echo "PET=DOG" >> "$GITHUB_OUTPUT”

### Recurso de estudio

[Comandos de flujo de trabajo para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-commands-for-github-actions#setting-an-output-parameter)

## Question 038

### Q38: Which of these is a way of using `action_state` in `step_two`?

```yaml
  steps:
    - name: Set the value
      id: step_one
      run: |
        echo "action_state=yellow" >> "$GITHUB_ENV"
    - name: Use the value
      id: step_two
      run: ?
```

- run: echo "$action_state”

### P38: ¿Cuál de estas es una forma de utilizar `action_state`in `step_two`?

```yaml
  steps:
    - name: Set the value
      id: step_one
      run: |
        echo "action_state=yellow" >> "$GITHUB_ENV"
    - name: Use the value
      id: step_two
      run: ?
```

- run: echo "$action_state”

### Recurso de estudio

[Comandos de flujo de trabajo para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-commands-for-github-actions#example-of-writing-an-environment-variable-to-github_env)

## Question 039

### **Q39: Is this statement true? `Workflows can be reused, but a reusable workflow cannot call another reusable workflow.`**

- False

### P39: ¿Es cierta esta afirmación? Los flujos de trabajo se pueden reutilizar, pero un flujo de trabajo reutilizable no puede llamar a otro flujo de trabajo reutilizable.

- Falso

### Recurso de estudio

[Reusing workflows - GitHub Docs](https://docs.github.com/en/actions/how-tos/sharing-automations/reusing-workflows#nesting-reusable-workflows)

## Question 040

### Q40: In the following example, `workflow A` passes all of its secrets to `workflow B`, by using the inherit keyword. Then `workflow B` calls `workflow C`. Which statement regarding `secrets` is true for that example?

```yaml
  jobs:
    workflowA-calls-workflowB:
      uses: octo-org/example-repo/.github/workflows/B.yml@main
      secrets: inherit

```

```yaml
  jobs:
    workflowB-calls-workflowC:
      uses: different-org/example-repo/.github/workflows/C.yml@main
```

- All secrets available to `workflow A` will be also available to `workflow B`, but not to `workflow C`

### P40: En el siguiente ejemplo, `workflow A`se transfieren todos sus secretos a `workflow B`, mediante la palabra clave "heredar". Luego, `workflow B`se llama a `workflow C`. ¿Cuál de las siguientes afirmaciones `secrets`es verdadera en este ejemplo?

```yaml
  jobs:
    workflowA-calls-workflowB:
      uses: octo-org/example-repo/.github/workflows/B.yml@main
      secrets: inherit
```

```yaml
  jobs:
    workflowB-calls-workflowC:
      uses: different-org/example-repo/.github/workflows/C.yml@main
```

- Todos los secretos disponibles para `workflow A`estarán también disponibles para `workflow B`, pero no para`workflow C`

### Recurso de estudio

[Reusing workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/reusing-workflows#passing-secrets-to-nested-workflows)

## Question 041

### **Q41: When should you use `caching`?**

- When you want to reuse files that don't change often between jobs or workflow runs, such as build dependencies from a package management system.

### **P41: ¿Cuándo debería utilizarse `caching`?**

- Cuando desee reutilizar archivos que no cambian con frecuencia entre trabajos o ejecuciones de flujo de trabajo, como dependencias de compilación de un sistema de administración de paquetes.

### Recurso de estudio

[Caching dependencies to speed up workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows)

## Question 042

### **Q42: When should you use `artifacts`? (Select two.)**

- Use artifacts to save files produced by a job to view after a workflow run has ended, such as test results or build logs.
- Use artifacts to save binaries produced by a build job to use in a subsequent deploy job to deploy a new version of an application

### **P42: ¿Cuándo debería utilizar `artifacts`? (Seleccione dos.)**

- Utilice artefactos para guardar archivos producidos por un trabajo para verlos después de que finalice la ejecución de un flujo de trabajo, como resultados de pruebas o registros de compilación.
- Utilice artefactos para guardar binarios producidos por un trabajo de compilación para usarlos en un trabajo de implementación posterior para implementar una nueva versión de una aplicación

### Recurso de estudio

[Storing and sharing data from a workflow - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow#about-workflow-artifacts)

## Question 043

### **Q43: If a workflow runs on a `feature-a` branch, can it restore `caches` created in the default `main` branch?**

- Yes, all branches can restore caches created on the default branch

### **P43: Si un flujo de trabajo se ejecuta en una `feature-a`rama, ¿puede restaurar `caches`lo creado en la rama predeterminada `main`?**

- Sí, todas las ramas pueden restaurar cachés creados en la rama predeterminada

### Recurso de estudio

[Caching dependencies to speed up workflows - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows#restrictions-for-accessing-a-cache)

## Question 044

### **Q44: To access an `artifact` that was created in another, previously triggered workflow run you can:**

- You cannot access `artifacts` that were created in a different workflow run

### P44: Para acceder a un `artifact`archivo creado en otra ejecución de flujo de trabajo activada previamente, puede:

- No se puede acceder `artifacts` a los que se crearon en una ejecución de flujo de trabajo diferente

### Recurso de estudio

[Storing and sharing data from a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow#about-workflow-artifacts)

## Question 045

### **Q45: What should you use to store coverage reports or screenshots generated during a workflow that runs automated testing for a repository?**

- Artifacts

### P45: ¿Qué debería usar para almacenar informes de cobertura o capturas de pantalla generados durante un flujo de trabajo que ejecuta pruebas automatizadas para un repositorio?

- Artefactos

### Recurso de estudio

[Storing and sharing data from a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow#comparing-artifacts-and-dependency-caching)

## Question 046

### **Q46: You can only upload a single file at a time when using `actions/upload-artifact` action**

- false

### P46: Solo puedes cargar un solo archivo a la vez cuando usas `actions/upload-artifact`la acción

- falso

### Recurso de estudio

[Storing and sharing data from a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow#uploading-build-and-test-artifacts)

## Question 047

### **Q47: In job `deploy`, if you want to access binaries (containing your application) that were created in job `build` you should**

- upload the binaries as artifacts in `build` and download them in `deploy`

### **P47: En el trabajo `deploy`, si desea acceder a los binarios (que contienen su aplicación) que se crearon en el trabajo, `build`debe**

- cargar los binarios como artefactos `build`y descargarlos en`deploy`

### Recurso de estudio

[Storing and sharing data from a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/storing-and-sharing-data-from-a-workflow#comparing-artifacts-and-dependency-caching)

## Question 048

### **Q48: A job called `job2` is using artifacts created in `job1`. Therefore it's important to make sure `job1` finishes before `job2` starts looking for the artifacts. How should you create that dependency?**

- create this dependency using the `needs` keyword in `job2`

### **P48: Un trabajo llamado `job2`utiliza artefactos creados en [nombre del trabajo] `job1`. Por lo tanto, es importante asegurarse de que `job1`finalice antes de `job2`comenzar a buscar los artefactos. ¿Cómo se debe crear esa dependencia?**

- Crea esta dependencia usando la `needs`palabra clave in`job2`

### Recurso de estudio

[Workflow syntax for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idneeds)

## Question 049

### **Q49: Which is true about `Starter Workflows` ? (Select three.)**

- Your organization can create custom starter workflows for users in your organization
- GitHub provides and maintains starter workflows for different categories, languages and tooling
- They allow users to leverage ready-to-use (or requiring minimal changes) workflow templates

### **P49: ¿Cuál de las siguientes afirmaciones es verdadera `Starter Workflows`? (Seleccione tres).**

- GitHub proporciona y mantiene flujos de trabajo de inicio para diferentes categorías, idiomas y herramientas.
- Su organización puede crear flujos de trabajo de inicio personalizados para los usuarios de su organización
- Permiten a los usuarios aprovechar plantillas de flujo de trabajo listas para usar (o que requieren cambios mínimos)

### Recurso de estudio

[Creating workflow templates for your organization - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/creating-workflow-templates-for-your-organization)

## Question 050

### **Q50: Secrets and configuration variables can be scoped to: (Select three.)**

- An environment in a repository
- A single repository
- The entire organization, or selected repositories in an organization

### **P50: Los secretos y las variables de configuración se pueden limitar a: (seleccione tres).**

- Un único repositorio
- Un entorno en un repositorio
- Toda la organización o repositorios seleccionados en una organización

### Recurso de estudio

[Sharing workflows, secrets, and runners with your organization - GitHub Docs](https://docs.github.com/en/actions/how-tos/administering-github-actions/sharing-workflows-secrets-and-runners-with-your-organization#sharing-secrets-and-variables-within-an-organization)

## Question 051

### **Q51: What are the three types of Actions?**

- `Docker container actions`, `JavaScript Actions`, `Composite Actions`

### **P51: ¿Cuáles son los tres tipos de acciones ?**

- `Docker container actions`, `JavaScript Actions`, `Composite Actions`

### Recurso de estudio

[Acercad e las acciones personalizadas - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-custom-actions#types-of-actions)

## Question 052

### **Q52: Is this statement true? `Docker container actions are usually slower than JavaScript actions`**

- true

### **P52: ¿Es verdadera esta afirmación? Las acciones del contenedor Docker suelen ser más lentas que las acciones de JavaScript**

- verdadero

## Question 053

### **Q53: When creating a custom GitHub Action you have to store the source code in `.github/workflows` directory**

- false

### **P53: Al crear una acción de GitHub personalizada, debe almacenar el código fuente en `.github/workflows`el directorio**

- falso

### Recurso de estudio

[Acercad e las acciones personalizadas - Documentación de GitHub](https://docs.github.com/es/actions/concepts/workflows-and-actions/about-custom-actions#choosing-a-location-for-your-action)

## Question 054

### Q54: When creating custom GitHub Actions - in what file does all the action `metadata` have to be defined?

Metadata examples: name, description, outputs or required inputs

- In the `action.yml` or `action.yaml` file in the action repository

### P54 : Al crear acciones de GitHub personalizadas, ¿en qué archivo se `metadata`deben definir todas las acciones?

Ejemplos de metadatos: nombre, descripción, salidas o entradas requeridas

- En el archivo `action.yml`o `action.yaml`en el repositorio de acciones

### Recurso de estudio

[Sintaxis de metadatos para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/metadata-syntax-for-github-actions)

## Question 055

### **Q55: A workflow was initially run on `commit A` and failed. You fixed the workflow with the subsequent `commit B`. When you re-run that workflow it will run with code from which commit?**

- It will run with code from `commit A`

### **P55: Se ejecutó inicialmente un flujo de trabajo `commit A`y falló. Corrigió el flujo de trabajo con el siguiente comando `commit B`. Al volver a ejecutarlo, ¿se ejecutará con el código de qué confirmación?**

- Se ejecutará con el código de`commit A`

### Recurso de estudio

[Re-running workflows and jobs - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/re-running-workflows-and-jobs#about-re-running-workflows-and-jobs)

## Question 056

### **Q56: How can you require manual approvals by a maintainer if the workflow run is targeting the `production` environment?**

- Using deployment protection rules

### **P56: ¿Cómo se pueden exigir aprobaciones manuales por parte de un mantenedor si la ejecución del flujo de trabajo tiene como objetivo el `production`entorno?**

- Uso de reglas de protección de implementación

### Recurso de estudio

[Managing environments foFr deployment - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-deployments/managing-environments-for-deployment)

## Question 057

### **Q57: Which is true about environments?**

- Each job in a workflow can reference a single environment.

### **P57: ¿Cuál de estas afirmaciones es cierta acerca del medio ambiente?**

- Cada trabajo en un flujo de trabajo puede hacer referencia a un único entorno.

## Question 058

### **Q58: When using GitHub Actions to access resources in one of the cloud providers (such as AWS, Azure or GCP) the safest and recommended way to authenticate is**

- Using OIDC

### P58: Al usar GitHub Actions para acceder a recursos en uno de los proveedores de la nube (como AWS, Azure o GCP), la forma más segura y recomendada de autenticarse es

- Uso de OIDC

### Recurso de estudio

[About security hardening with OpenID Connect - GitHub Docs](https://docs.github.com/en/actions/concepts/security/about-security-hardening-with-openid-connect)

## Question 059

### **Q59: Your open-source publicly available repository contains a workflow with a `pull_request` event trigger. How can you require approvals for workflow runs triggered from forks of your repository?**

- Setup required approvals for fork runs in the repository

### **P59: Su repositorio público de código abierto contiene un flujo de trabajo con un `pull_request`activador de eventos. ¿Cómo puede exigir aprobaciones para las ejecuciones de flujo de trabajo activadas desde bifurcaciones de su repositorio?**

- Configurar las aprobaciones necesarias para las ejecuciones de bifurcación en el repositorio

### Recurso de estudio

[Approving workflow runs from public forks - GitHub Docs](https://docs.github.com/en/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/approving-workflow-runs-from-public-forks#about-workflow-runs-from-public-forks)

## Question 060

### **Q60: Which of the following default environment variables contains the name of the person or app that initiated the workflow run?**

- GITHUB_ACTOR

### P60: ¿Cuál de las siguientes variables de entorno predeterminadas contiene el nombre de la persona o aplicación que inició la ejecución del flujo de trabajo?

- `GITHUB_ACTOR`

### Recurso de estudio

[Store information in variables - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#default-environment-variables)

## Question 061

### **Q61: Which of the following are default environment variables in GitHub Actions? (Select three.)**

- GITHUB_REPOSITORY
- GITHUB_ACTOR
- GITHUB_WORKFLOW

### **P61: ¿Cuáles de las siguientes son variables de entorno predeterminadas en GitHub Actions? (Seleccione tres).**

- GITHUB_REPOSITORY
- GITHUB_ACTOR
- GITHUB_WORKFLOW

### Recurso de estudio

[Store information in variables - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#default-environment-variables)

## Question 062

### **Q62: Your organization defines a secret `SomeSecret`, however when you reference that secret in a workflow using `${{ secrets.SomeSecret }}` it provides a different value than expected. What may be the reason for that?**

- The secret `SomeSecret` is also declared in repository scope

### **P62: Su organización define un secreto `SomeSecret`; sin embargo, al hacer referencia a él en un flujo de trabajo, `${{ secrets.SomeSecret }}`su uso proporciona un valor diferente al esperado. ¿Cuál podría ser el motivo?**

- El secreto SomeSecret también se declara en el ámbito del repositorio.

### Recurso de estudio

[Using secrets in GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/security-for-github-actions/security-guides/using-secrets-in-github-actions#naming-your-secrets)

## Question 063

### **Q63: Which is a correct way to print a debug message?63**

- echo "::debug::Watch out here!”

### **P63: ¿Cuál es la forma correcta de imprimir un mensaje de depuración?**

- echo "::debug::Watch out here!”

### Recurso de estudio

[Workflow commands for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-commands-for-github-actions#example-setting-a-debug-message)

## Question 064

### **Q64: How can organizations which are using GitHub Enterprise Server enable automatic syncing of third party GitHub Actions hosted on GitHub.com to their GitHub Enterprise Server instance?**

- Using GitHub Connect

### **P64: ¿Cómo pueden las organizaciones que utilizan GitHub Enterprise Server habilitar la sincronización automática de acciones de GitHub de terceros alojadas en GitHub.com con su instancia de GitHub Enterprise Server?**

- Uso de GitHub Connect

### Recurso de estudio

[Enabling automatic access to GitHub.com actions using GitHub Connect - GitHub Enterprise Server 3.6 Docs](https://docs.github.com/en/enterprise-server@3.6/admin/github-actions/managing-access-to-actions-from-githubcom/enabling-automatic-access-to-githubcom-actions-using-github-connect)

## Question 065

### **Q65: Where can you find network connectivity logs for a GitHub self-hosted-runner?**

- In the `_diag` folder directly on the runner machine

### **P65: ¿Dónde puedo encontrar registros de conectividad de red para un ejecutor autohospedado de GitHub?**

- En la `_diag`carpeta directamente en la máquina del corredor

### Recurso de estudio

[Monitoring and troubleshooting self-hosted runners - GitHub Docs](https://docs.github.com/en/actions/how-tos/hosting-your-own-runners/managing-self-hosted-runners/monitoring-and-troubleshooting-self-hosted-runners#checking-self-hosted-runner-network-connectivity)

## Question 066

### **Q66: How can you validate that your GitHub self-hosted-runner can access all required GitHub services?**

- Using a GitHub provided script on the runner machine

### **P66: ¿Cómo puede validar que su ejecutor autohospedado de GitHub pueda acceder a todos los servicios de GitHub necesarios?**

- Usando un script proporcionado por GitHub en la máquina ejecutora

### Recurso de estudio

[Monitoring and troubleshooting self-hosted runners - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/hosting-your-own-runners/managing-self-hosted-runners/monitoring-and-troubleshooting-self-hosted-runners#checking-self-hosted-runner-network-connectivity)

## Question 067

### **Q67: Which is the correct way of triggering a job only if configuration variable `MY_VAR` has the value of `MY_VALUE`?**

```yaml
# By creating the following conditional on job level
my-job:
 if: ${{ vars.MY_VAR == 'MY_VALUE' }}
```

### **P67: ¿Cuál es la forma correcta de activar un trabajo solo si la variable de configuración `MY_VAR`tiene el valor de `MY_VALUE`?**

```yaml
# Creando la siguiente condición a nivel de trabajo
my-job:
 if: ${{ vars.MY_VAR == 'MY_VALUE' }}
```

### Recurso de estudio

[Accessing contextual information about workflow runs - GitHub Docs](https://docs.github.com/en/actions/reference/accessing-contextual-information-about-workflow-runs#example-usage-of-the-vars-context)

## Question 068

### **Q68: To run a `step` only if the secret `MY_SECRET` has been set, you can:**

```yaml
# Set the secret MY_SECRET as a job level environment variable,
# then reference that environment variable to conditionally run
# that step
my-job:
 runs-on: ubuntu-latest
 env:
   my_secret: ${{ secrets.MY_SECRET }}
 steps:
   - if: ${{ env.my_secret != '' }}
```

### P68: Para ejecutar `step`solo si se ha configurado el secreto `MY_SECRET`, puede:

```yaml
# Establezca el secreto MY_SECRET como una variable de entorno a nivel
# de trabajo y luego haga referencia a esa variable de entorno para
# ejecutar ese paso condicionalmente
my-job:
 runs-on: ubuntu-latest
 env:
   my_secret: ${{ secrets.MY_SECRET }}
 steps:
   - if: ${{ env.my_secret != '' }}
```

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#example-using-secrets)

## Question 069

### **Q69: How can you use the GitHub API to download workflow run logs?**

- `GET /repos/{owner}/{repo}/actions/runs/{run_id}/logs`

### P69: ¿Cómo se puede utilizar la API de GitHub para descargar registros de ejecución del flujo de trabajo?

- `GET /repos/{owner}/{repo}/actions/runs/{run_id}/logs`

### Recurso de estudio

[Puntos de conexión de API de REST para ejecuciones de flujo de trabajo - Documentación de GitHub](https://docs.github.com/es/rest/actions/workflow-runs?apiVersion=2022-11-28#download-workflow-run-logs)

## Question 070

### **Q70: How can you use the GitHub API to create or update a repository secret?**

- `PUT /repos/{owner}/{repo}/actions/secrets/{secret_name}`

### P70: ¿Cómo se puede utilizar la API de GitHub para crear o actualizar un secreto de repositorio?

- `PUT /repos/{owner}/{repo}/actions/secrets/{secret_name}`

### Recurso de estudio

[REST API endpoints for GitHub Actions Secrets - GitHub Docs](https://docs.github.com/en/rest/actions/secrets?create-or-update-a-repository-secret=&apiVersion=2022-11-28#create-or-update-a-repository-secret)

## Question 071

### **Q71: How can you override an organization-level GitHub Secret `API_KEY` with a different value when working within a repository? (Select two.)**

- By creating a environment secret with the same name `API_KEY`
- By creating a repository secret with the same name `API_KEY`

### **P71: ¿Cómo se puede anular un secreto de GitHub a nivel de organización `API_KEY`con un valor diferente al trabajar dentro de un repositorio? (Seleccione dos).**

- Creando un secreto de entorno con el mismo nombre`API_KEY`
- Creando un secreto de repositorio con el mismo nombre`API_KEY`

### Recurso de estudio

[Using secrets in GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/security-for-github-actions/security-guides/using-secrets-in-github-actions?tool=cli)

## Question 072

### **Q72: What components can be reused within a GitHub Organization? (Select four.)**

- Self Hosted Runners
- Workflow Templates
- Secrets
- Configuration Variables

### **P72: ¿Qué componentes se pueden reutilizar dentro de una organización de GitHub? (Seleccione cuatro).**

- Corredores autoalojados
- Plantillas de flujo de trabajo
- Misterios
- Variables de configuración

## Question 073

### Q73: How many jobs will be executed in the following workflow?

```yaml
jobs:
  matrix-job:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        pet: [cat, dog]
        color: [pink, brown]
        include:
          - color: white
            pet: dog
    steps:
      - run: echo "Hello ${{ matrix.color }} ${{ matrix.pet }}"
```

- 5

### P73: ¿Cuántos trabajos se ejecutarán en el siguiente flujo de trabajo?

```yaml
jobs:
  matrix-job:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        pet: [cat, dog]
        color: [pink, brown]
        include:
          - color: white
            pet: dog
    steps:
      - run: echo "Hello ${{ matrix.color }} ${{ matrix.pet }}"
```

- 5

### Recurso de estudio

[Running variations of jobs in a workflow - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow#using-a-matrix-strategy)

## Question 074

### **Q74: Which of the following default environment variables contains the full name (e.g `octocat/hello-world`) of the repository where the workflow is running?**

- GITHUB_REPOSITORY

### **P74: ¿Cuál de las siguientes variables de entorno predeterminadas contiene el nombre completo (por ejemplo, `octocat/hello-world`) del repositorio donde se ejecuta el flujo de trabajo?**

- GITHUB_REPOSITORY

### Recurso de estudio

[Store information in variables - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#default-environment-variables)

## Question 075

### **Q75: In a workflow that has multiple jobs, all running on GitHub-hosted runners, is it true that all jobs are guaranteed to run on the same runner machine?**

- No

### **P75: En un flujo de trabajo que tiene varios trabajos, todos ejecutándose en ejecutores alojados en GitHub, ¿es cierto que se garantiza que todos los trabajos se ejecutarán en la misma máquina ejecutora?**

- No

### Recurso de estudio

[Choosing the runner for a job - GitHub Docs](https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners)

## Question 076

### **Q76: What's the maximum amount of reusable workflows that can be called from a single workflow file?**

- 20

### **P76: ¿Cuál es la cantidad máxima de flujos de trabajo reutilizables que se pueden llamar desde un solo archivo de flujo de trabajo?**

- 20

### Recurso de estudio

[Reusing workflows - GitHub Docs](https://docs.github.com/en/actions/using-workflows/reusing-workflows#limitations)

## Question 077

### **Q77: What is a self-hosted runner?**

- A self-hosted runner is a system that you deploy and manage to execute jobs from GitHub Actions on [GitHub.com](http://github.com/)

### **P77: ¿Qué es un corredor autoalojado?**

- Un ejecutor autohospedado es un sistema que usted implementa y administra para ejecutar trabajos desde GitHub Actions en [GitHub.com](http://github.com/)

### Recurso de estudio

[About self-hosted runners - GitHub Docs](https://docs.github.com/en/actions/concepts/runners/about-self-hosted-runners)

## Question 078

### **Q78: Which of the following is a correct statement about GitHub Workflows and Actions?**

- Each workflow is composed of one or more job which is composed of one or more step, and each step is an action or a script

### **P78: ¿Cuál de las siguientes es una afirmación correcta sobre los flujos de trabajo y las acciones de GitHub?**

- Cada flujo de trabajo se compone de uno o más trabajos que a su vez se componen de uno o más pasos, y cada paso es una acción o un script.

### Recurso de estudio

[Understanding GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/get-started/understanding-github-actions)

## Question 079

### **Q79: On which commit and branch do scheduled workflows run in GitHub Actions?**

- Scheduled workflows run on the latest commit on the repository default branch.

### **P79: ¿En qué confirmación y rama se ejecutan los flujos de trabajo programados en GitHub Actions?**

- Los flujos de trabajo programados se ejecutan en la última confirmación en la rama predeterminada del repositorio.

### Recurso de estudio

[Events that trigger workflows - GitHub Docs](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#schedule)

## Question 080

### **Q80: What is the correct syntax for setting the directory for all `run` commands in a workflow?**

```yaml
# set working-directory under defaults.run
 defaults:
     run:
         shell: bash
         working-directory: ./scripts
```

### **P80: ¿Cuál es la sintaxis correcta para configurar el directorio para todos `run`los comandos en un flujo de trabajo?**

```yaml
# establecido working-directorybajodefaults.run
 defaults:
     run:
         shell: bash
         working-directory: ./scripts
```

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#defaultsrunworking-directory)

## Question 081

### **Q81: How can you reuse a defined workflow in multiple repositories? (Choose two.)**

- By using workflow templates
- By defining the workflow in a central repository

### **P81: ¿Cómo se puede reutilizar un flujo de trabajo definido en varios repositorios? (Elija dos opciones).**

- Mediante el uso de plantillas de flujo de trabajo
- Al definir el flujo de trabajo en un repositorio central

### Recurso de estudio

[Creating workflow templates for your organization - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/sharing-automations/creating-workflow-templates-for-your-organization)

## Question 082

### **Q82: How can you ensure a job runs only on a specific branch?**

- By using the branches filter

### **P82: ¿Cómo puede garantizar que un trabajo se ejecute solo en una rama específica?**

- Usando el filtro de ramas

### Recurso de estudio

[Workflow syntax for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#using-filters)

## Question 083

### **Q83: What does the `needs` keyword do in a GitHub Actions workflow?**

- Specifies the dependencies of a job

### **P83: ¿Qué hace la `needs`palabra clave en un flujo de trabajo de GitHub Actions?**

- Especifica las dependencias de un trabajo

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idneeds)

## Question 084

### **Q84: Which keyword allows you to define environment variables in a GitHub Actions workflow?**

- env

### **P84: ¿Qué palabra clave le permite definir variables de entorno en un flujo de trabajo de GitHub Actions?**

- env

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idenv)

## Question 085

### **Q85: What is the purpose of the `with` keyword in a GitHub Actions workflow?**

- To specify input parameters for an action

### **P85: ¿Cuál es el propósito de la `with`palabra clave en un flujo de trabajo de GitHub Actions?**

- Para especificar parámetros de entrada para una acción

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepswith)

## Question 086

### **Q86: Which of the following GitHub Actions syntax is used to run multiple commands in a single step?**

- Using a multiline string with |

### **P86: ¿Cuál de las siguientes sintaxis de GitHub Actions se utiliza para ejecutar varios comandos en un solo paso?**

- Usando una cadena multilineal con |

### Recurso de estudio

[Workflow commands for GitHub Actions - GitHub Enterprise Cloud Docs](https://docs.github.com/en/enterprise-cloud@latest/actions/reference/workflow-commands-for-github-actions#example-of-a-multiline-string)

## Question 087

### **Q87: How can you cache dependencies to speed up workflow execution?**

- Using the actions/cache action

### **P87: ¿Cómo se pueden almacenar en caché las dependencias para acelerar la ejecución del flujo de trabajo?**

- Uso de la acción acciones/caché

### Recurso de estudio

[Caching dependencies to speed up workflows - GitHub Enterprise Cloud Docs](https://docs.github.com/es/enterprise-cloud@latest/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows#about-caching-workflow-dependencies)

## Question 088

### **Q88: What does the `matrix` keyword do in a GitHub Actions workflow?**

- Allows defining multiple job configurations to run in parallel

### **P88: ¿Qué hace la `matrix`palabra clave en un flujo de trabajo de GitHub Actions?**

- Permite definir múltiples configuraciones de trabajos para ejecutar en paralelo

### Recurso de estudio

[Running variations of jobs in a workflow - GitHub Enterprise Cloud Docs](https://docs.github.com/es/enterprise-cloud@latest/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow)

## Question 089

### **Q89: Which of the following can be used to limit the number of concurrent jobs running in a GitHub Actions workflow?**

- concurrency

### **P89: ¿Cuál de las siguientes opciones se puede utilizar para limitar la cantidad de trabajos simultáneos que se ejecutan en un flujo de trabajo de GitHub Actions?**

- concurrencia

### Recurso de estudio

[Control the concurrency of workflows and jobs - GitHub Enterprise Cloud Docs](https://docs.github.com/es/enterprise-cloud@latest/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/control-the-concurrency-of-workflows-and-jobs)

## Question 090

### **Q90: What is the default timeout for a GitHub Actions job?**

- 360 minutes

### **P90: ¿Cuál es el tiempo de espera predeterminado para un trabajo de GitHub Actions?**

- 360 minutos

### Recurso de estudio

[Usage limits, billing, and administration - GitHub Docs](https://docs.github.com/en/actions/concepts/overview/usage-limits-billing-and-administration#usage-limits)

## Question 091

### **Q91: How can you specify the operating system for a job in GitHub Actions?**

- Using the runs-on keyword

### **P91: ¿Cómo se puede especificar el sistema operativo para un trabajo en GitHub Actions?**

- Uso de la palabra clave runs-on

### Recurso de estudio

[Workflow syntax for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on)

## Question 092

### **Q92: In a GitHub Actions workflow, how do you specify a specific version of Node.js to use in a job?**

```yaml
uses: actions/setup-node@v4
	with:
	 node-version: 20
```

### **P92: En un flujo de trabajo de GitHub Actions, ¿cómo se especifica una versión específica de Node.js para usar en un trabajo?**

```yaml
uses: actions/setup-node@v4
	with:
	 node-version: 20
```

### Recurso de estudio

[Building and testing Node.js - GitHub Docs](https://docs.github.com/en/actions/how-tos/use-cases-and-examples/building-and-testing/building-and-testing-nodejs#specifying-the-nodejs-version)

## Question 093

### **Q93: How do you reference a secret stored in GitHub Secrets in a workflow?**

- ${{ secrets.SECRET_NAME }}

### **P93: ¿Cómo se hace referencia a un secreto almacenado en GitHub Secrets en un flujo de trabajo?**

- ${{ secrets.SECRET_NAME }}

### Recurso de estudio

[Using secrets in GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/security-for-github-actions/security-guides/using-secrets-in-github-actions#using-secrets-in-a-workflow)

## Question 094

### **Q94: What is the default shell used by GitHub Actions on Windows runners?**

- powershell

### **P94: ¿Cuál es el shell predeterminado que utilizan las Acciones de GitHub en los ejecutores de Windows?**

- powershell

### Recurso de estudio

[GitHub Actions default shell on Windows runners is changing to PowerShell - GitHub Changelog](https://github.blog/changelog/2019-10-17-github-actions-default-shell-on-windows-runners-is-changing-to-powershell/)

## Question 095

### **Q95: Which of the following statements are true about adding a self-hosted runner in GitHub Actions? (Choose three.)**

- You can add a self-hosted runner to an enterprise
- You can add a self-hosted runner to an organization
- You can add a self-hosted runner to a repository

### **P95: ¿Cuáles de las siguientes afirmaciones son verdaderas sobre agregar un ejecutor autohospedado en GitHub Actions? (Elija tres).**

- Puede agregar un ejecutor autohospedado a una empresa
- Puedes agregar un ejecutor autohospedado a una organización
- Puede agregar un ejecutor autohospedado a un repositorio

### Recurso de estudio

[Adding self-hosted runners - GitHub Docs](https://docs.github.com/en/actions/how-tos/hosting-your-own-runners/managing-self-hosted-runners/adding-self-hosted-runners#adding-a-self-hosted-runner-to-a-repository)

## Question 096

### **Q96: Select the default environment variable that contains the operating system of the runner executing the job**

- RUNNER_OS

### **P96: Seleccione la variable de entorno predeterminada que contiene el sistema operativo del ejecutor que ejecuta el trabajo**

- RUNNER_OS

### Recurso de estudio

[Store information in variables - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#default-environment-variables)

## Question 097

### **Q97: How does the `actions/cache` action in GitHub Actions handle a cache miss?**

- by automatically creating a new cache if the job is completed successfully

### **P97: ¿Cómo `actions/cache`maneja la acción en GitHub Actions una falla de caché?**

- creando automáticamente una nueva caché si el trabajo se completa correctamente

### Recurso de estudio

[Caching dependencies to speed up workflows - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows#managing-caches)

## Question 098

### **Q98: How can you specify the schedule of a GitHub actions workflow to run on weekdays only?**

- use the on: schedule: cron event trigger

### **P98: ¿Cómo se puede especificar el cronograma de un flujo de trabajo de acciones de GitHub para que se ejecute solo los días de semana?**

- Utilice el disparador de evento cron on: schedule:

### Recurso de estudio

[Events that trigger workflows - GitHub Docs](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#schedule)

## Question 099

### **Q99: What is the recommended approach for storing secrets larger than 48 KB?**

- encrypt and store secrets in the repository but keep the decryption passphrase as a secret

### **P99: ¿Cuál es el enfoque recomendado para almacenar secretos de más de 48 KB?**

- Cifrar y almacenar secretos en el repositorio, pero mantener la frase de contraseña de descifrado como secreto.

### Recurso de estudio

[Using secrets in GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/security-for-github-actions/security-guides/using-secrets-in-github-actions#limits-for-secrets)

## Question 100

### **Q100: Select status check functions in GitHub Actions**

- `success()`, `always()`, `cancelled()` and `failure()`

### **P100: Seleccionar funciones de verificación de estado en GitHub Actions**

- `success()`, `always()`, `cancelled()` and `failure()`

### Recurso de estudio

[Evaluate expressions in workflows and actions - GitHub Docs](https://docs.github.com/en/actions/reference/evaluate-expressions-in-workflows-and-actions#status-check-functions)

## Question 101

### **Q101: How do you ensure that `Upload Failure test report` step is executed only if `Run Tests` step fails?**

```yaml
 - name: Run Tests
   id: run-tests
   run: npm run test

 - name: Upload Failure test report
   if: failure() && steps.run-tests.outcome == 'failure'
   run: actions/upload-artifact@v3
   with:
     name: test-report
     path: test-reports.html
```

### **P101 : ¿Cómo se garantiza que `Upload Failure test report`el paso se ejecute solo si `Run Tests`el paso falla?**

```yaml
 - name: Run Tests
   id: run-tests
   run: npm run test

 - name: Upload Failure test report
   if: failure() && steps.run-tests.outcome == 'failure'
   run: actions/upload-artifact@v3
   with:
     name: test-report
     path: test-reports.html
```

### Recurso de estudio

[Evaluación de expresiones en flujos de trabajo y acciones - Documentación de GitHub](https://docs.github.com/es/actions/reference/evaluate-expressions-in-workflows-and-actions#status-check-functions)

## Question 102

### **Q102: Which context holds information about the event that triggered a workflow run?**

- github.event

### **P102: ¿Qué contexto contiene información sobre el evento que desencadenó la ejecución de un flujo de trabajo?**

- github.event

### Recurso de estudio

[Triggering a workflow - GitHub Docs](https://docs.github.com/en/actions/using-workflows/triggering-a-workflow#using-event-information)

## Question 103

### **Q103: In GitHub Actions, if you define both branches and paths filter, what is the effect on the workflow execution?**

- the workflow will only run when both `branches` and `paths` are satisfied

### **P103: En GitHub Actions, si define filtros de ramas y rutas, ¿cuál es el efecto en la ejecución del flujo de trabajo?**

- El flujo de trabajo solo se ejecutará cuando tanto `branches`como `paths`estén satisfechos

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#onpull_requestpull_request_targetbranchesbranches-ignore)

## Question 104

### **Q104: What is the recommended practice for treating environment variables in GitHub Actions, regardless of the operating system and shell used?**

- treat environment variables as case-sensitive

### **P104: ¿Cuál es la práctica recomendada para tratar las variables de entorno en GitHub Actions, independientemente del sistema operativo y el shell utilizados?**

- Tratar las variables de entorno como sensibles a mayúsculas y minúsculas

### Recurso de estudio

[Comandos de flujo de trabajo para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-commands-for-github-actions#setting-an-environment-variable)

## Question 105

### **Q105: Which of the following statements accurately describes the behavior of workflow jobs referencing an environment's protection rules?**

- workflow jobs won't start until all the environment's protection rules pass

### **P105: ¿Cuál de las siguientes afirmaciones describe con precisión el comportamiento de los trabajos de flujo de trabajo que hacen referencia a las reglas de protección de un entorno?**

- Los trabajos de flujo de trabajo no comenzarán hasta que se cumplan todas las reglas de protección del entorno

### Recurso de estudio

[Managing environments for deployment - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-deployments/managing-environments-for-deployment)

## Question 106

### **Q106: What is the purpose of the `restore-keys` parameter in `actions/cache` in GitHub Actions?**

- provide alternative keys to use in case of a cache miss

### **P106: ¿Cuál es el propósito del `restore-keys`parámetro en `actions/cache`GitHub Actions?**

- Proporcionar claves alternativas para usar en caso de una falla de caché

### Recurso de estudio

[Caching dependencies to speed up workflows - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows#managing-caches)

## Question 107

### **Q107: Which variable would you set to `true` in order to enable step debug logging?**

- ACTIONS_STEP_DEBUG

### **P107: ¿Qué variable configuraría `true`para habilitar el registro de depuración de pasos?**

- ACTIONS_STEP_DEBUG

### Recurso de estudio

[Enabling debug logging - GitHub Docs](https://docs.github.com/en/actions/how-tos/monitoring-and-troubleshooting-workflows/troubleshooting-workflows/enabling-debug-logging)

## Question 108

### Q108: Which configuration is appropriate for triggering a workflow to run on webhook events related to check_run actions?

```yaml
on:
 check_run:
     types: [rerequested, completed]
```

### **P109: ¿Qué configuración es adecuada para activar un flujo de trabajo para que se ejecute en eventos de webhook relacionados con acciones check_run?**

```yaml
on:
 check_run:
     types: [rerequested, completed]
```

### Recurso de estudio

[Events that trigger workflows - GitHub Docs](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#check_run)

## Question 109

### **Q109: What is the purpose of the `timeout-minutes` keyword in a step?**

- it limits the execution time for individual step

### **P109 : ¿Cuál es el propósito de la `timeout-minutes`palabra clave en un paso?**

- Limita el tiempo de ejecución de cada paso individual

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepstimeout-minutes)

## Question 110

### **Q110: Dave is creating a templated workflow for his organization. Where must Dave store the workflow files and associated metadata files for the templated workflow?**

- inside a directory named `workflow-templates` within a repository named `.github`

### **P 1 : Donde está creando un flujo de trabajo basado en plantillas para su organización. ¿Dónde debe almacenar los archivos del flujo de trabajo y los metadatos asociados?**

- inside a directory named `workflow-templates` within a repository named `.github`

### Recurso de estudio

[Creating workflow templates for your organization - GitHub Docs](https://docs.github.com/en/actions/how-tos/sharing-automations/creating-workflow-templates-for-your-organization)

## Question 111

### **Q111: Dave wants to be notified when a comment is created on an issue within a GitHub repository. Which event trigger should be used within the workflow configuration?**

- issue_comment

### **P111: Donde quiere recibir una notificación cuando se crea un comentario sobre un problema en un repositorio de GitHub. ¿Qué activador de evento debería usarse en la configuración del flujo de trabajo?**

- issue_comment

### Recurso de estudio

[Events that trigger workflows - Documentación de GitHub](https://docs.github.com/es/actions/reference/events-that-trigger-workflows#issue_comment)

## Question 112

### **Q112: What level of access is required on a GitHub repository in order to delete log files from workflow runs?**

- write

### **P113: ¿Qué nivel de acceso se requiere en un repositorio de GitHub para eliminar archivos de registro de las ejecuciones del flujo de trabajo?**

- escribir

### Recurso de estudio

[Using workflow run logs - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/monitoring-and-troubleshooting-workflows/monitoring-workflows/using-workflow-run-logs)

## Question 113

### Q113: What is true about the following workflow configuration if triggered against the `octo/my-dev-repo` repository?

```yaml
name: deploy-workflow
on: [push]
jobs:
    production-deploy:
        if: github.repository == 'octo/my-prod-repo'
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v4
            - uses: actions/setup-node@v4
              with:
                  node-version: '14'
            - run: npm install -g bats
```

- the `production-deploy` job will be marked as skipped

### P113 : ¿Qué es cierto acerca de la siguiente configuración de flujo de trabajo si se activa contra el `octo/my-dev-repo`repositorio?

```yaml
name: deploy-workflow
on: [push]
jobs:
    production-deploy:
        if: github.repository == 'octo/my-prod-repo'
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v4
            - uses: actions/setup-node@v4
              with:
                  node-version: '14'
            - run: npm install -g bats
```

- El `production-deploy`trabajo se marcará como omitido

### Recurso de estudio

[Using conditions to control job execution - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-when-your-workflow-runs/using-conditions-to-control-job-execution)

## Question 114

### Q114: How can you access the current values of variables in a matrix within a job in the example below:

```yaml
jobs:
    example_matrix:
        strategy:
            matrix:
                version: [10, 12, 14]
                os: [ubuntu-latest, windows-latest]
```

- reference variables through the `matrix` context with syntax like`matrix.version` and `matrix.os`

### P114 : ¿Cómo se puede acceder a los valores actuales de las variables en una matriz dentro de un trabajo en el siguiente ejemplo?

```yaml
jobs:
    example_matrix:
        strategy:
            matrix:
                version: [10, 12, 14]
                os: [ubuntu-latest, windows-latest]
```

- variables de referencia a través del `matrix`contexto con sintaxis como `matrix.version`y`matrix.os`

### Recurso de estudio

[Running variations of jobs in a workflow - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow#using-a-matrix-strategy)

## Question 115

### **Q115: What level of permission is required to re-run the workflows**

- write

### **P115 : ¿Qué nivel de permiso se requiere para volver a ejecutar los flujos de trabajo?**

- escritura

### Recurso de estudio

[Re-running workflows and jobs - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/re-running-workflows-and-jobs)

## Question 116

### **Q116: When can you delete workflow runs? (select two)**

- When workflow run is two weeks old
- When workflow run has been completed

### **P116: ¿Cuándo se pueden eliminar ejecuciones de flujo de trabajo? (seleccione dos)**

- Cuando la ejecución del flujo de trabajo tiene dos semanas
- Cuando se haya completado la ejecución del flujo de trabajo

### Recurso de estudio

[Deleting a workflow run - GitHub Docs](https://docs.github.com/en/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/deleting-a-workflow-run)

## Question 117

### **Q117: Who can bypass configured deployment protection rules to force deployment (by default)**

- Repository administrators

### **P117 : ¿Quién puede eludir las reglas de protección de implementación configuradas para forzar la implementación (de manera predeterminada)?**

- administradores del repositorio

### Recurso de estudio

[Managing environments for deployment - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/managing-workflow-runs-and-deployments/managing-deployments/managing-environments-for-deployment#allow-administrators-to-bypass-configured-protection-rules)

## Question 118

### Q118: How can you skip the following workflow run when you commit or create a PR?

```yaml
name: Build
on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    name: Extract artifact version
```

```yaml
# By including any one of the following keywords in the commit
# message or in the title of the pull-request
[skip ci]
[ci skip]
[no ci]
[skip actions]
[actions skip]
```

### P118 : ¿Cómo se puede omitir la siguiente ejecución del flujo de trabajo cuando se confirma o crea una solicitud PR?

```yaml
name: Build
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    name: Extract artifact version
```

```yaml
# Incluyéndose cualquiera de las siguientes palabras clave en el
# mensaje de confirmación o en el título de la solicitud de
# extracción
[skip ci]
[ci skip]
[no ci]
[skip actions]
[actions skip]
```

### Recurso de estudio

[Skipping workflow runs - GitHub Docs](https://docs.github.com/en/actions/how-tos/managing-workflow-runs-and-deployments/managing-workflow-runs/skipping-workflow-runs)

## Question 119

### **Q119: How can you determine if an action is a container action by looking at its action.yml file?**

- `runs.using` has `docker` as value

### **P119: ¿Cómo puedes determinar si una acción es una acción contenedora mirando su archivo action.yml?**

- `runs.using`tiene `docker`como valor

### Recurso de estudio

[Sintaxis de metadatos para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/metadata-syntax-for-github-actions#runs-for-docker-container-actions)

## Question 120

### **Q120: What is the correct syntax for specifying a cleanup script in a container action?**

```yaml
 runs:
   using: 'docker'
   image: 'Dockerfile'
   entrypoint: 'entrypoint.sh'
   post-entrypoint: 'cleanup.sh'
```

### **P120 : ¿Cuál es la sintaxis correcta para especificar un script de limpieza en una acción de contenedor?**

```yaml
 runs:
   using: 'docker'
   image: 'Dockerfile'
   entrypoint: 'entrypoint.sh'
   post-entrypoint: 'cleanup.sh'
```

### Recurso de estudio

[Sintaxis de metadatos para Acciones de GitHub - Documentación de GitHub](https://docs.github.com/es/actions/reference/metadata-syntax-for-github-actions#runspost-entrypoint)

## Question 121

### **Q121: What’s true about default variables? (choose three)**

- Default environment variables are set by GitHub and not defined in a workflow
- Currently, the value of the default CI environment variable can be overwritten, but it's not guaranteed this will always be possible
- Most of the default environment variables have a corresponding context property

### **P121 : ¿Qué es cierto acerca de las variables predeterminadas? (elige tres)**

- Las variables de entorno predeterminadas las establece GitHub y no se definen en un flujo de trabajo
- Actualmente, el valor de la variable de entorno CI predeterminada se puede sobrescribir, pero no se garantiza que esto siempre sea posible.
- La mayoría de las variables de entorno predeterminadas tienen una propiedad de contexto correspondiente

### Recurso de estudio

[Store information in variables - GitHub Docs](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#default-environment-variables)

## Question 122

### **Q122: What are the scopes defined for custom variables in a workflow? (choose three)**

- A specific step within a job, by using `jobs.<job_id>.steps[*].env`
- The entire workflow, by using `env` at the top level of the workflow file
- The contents of a job within a workflow, by using `jobs.<job_id>.env`

### **P122: ¿Cuáles son los alcances definidos para las variables personalizadas en un flujo de trabajo? (elija tres)**

- Un paso específico dentro de un trabajo, mediante el uso de`jobs.<job_id>.steps[*].env`
- Todo el flujo de trabajo, mediante el uso `env`en el nivel superior del archivo de flujo de trabajo
- El contenido de un trabajo dentro de un flujo de trabajo, mediante el uso de`jobs.<job_id>.env`

### Recurso de estudio

[Store information in variables - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables#defining-environment-variables-for-a-single-workflow)

## Question 123

### **Q123: What must be added to `actions/checkout` if `my-org/my-private-repo` is a private repository differing from the one containing the current workflow?**

```yaml
name: deploy-workflow
on: [push]
jobs:
    my-job:
        runs-on: ubuntu-latest
        steps:
          - name: "Checkout GitHub Action"
            uses: actions/checkout@v4
            with:
               repository: my-org/my-private-repo
               path: ./.github/actions/my-org/my-private-repo
```

```yaml
# Create a GitHub secret MY_ACCESS_TOKEN
with:
 repository: my-org/my-private-repo
 path: ./.github/actions/my-org/my-private-repo
 token: ${{ secrets.MY_ACCESS_TOKEN }}
```

### P123 : ¿Qué se debe agregar `actions/checkout`si `my-org/my-private-repo`un repositorio privado es diferente del que contiene el flujo de trabajo actual?

```yaml
name: deploy-workflow
on: [push]
jobs:
    my-job:
        runs-on: ubuntu-latest
        steps:
          - name: "Checkout GitHub Action"
            uses: actions/checkout@v4
            with:
               repository: my-org/my-private-repo
               path: ./.github/actions/my-org/my-private-repo
```

```yaml
# Crear un secreto de GitHubMY_ACCESS_TOKEN
with:
 repository: my-org/my-private-repo
 path: ./.github/actions/my-org/my-private-repo
 token: ${{ secrets.MY_ACCESS_TOKEN }}
```

### Recurso de estudio

[Sintaxis del flujo de trabajo para GitHub Actions - Documentación de GitHub](https://docs.github.com/es/actions/reference/workflow-syntax-for-github-actions#example-using-an-action-inside-a-different-private-repository-than-the-workflow)

## Question 124

### **Q124: Given the following configuration, how many jobs will GitHub Actions run when this matrix is evaluated?**

```yaml
strategy:
  matrix:
    os: [ubuntu-latest, windows-latest]
    node: [14, 16]
    include:
      - os: macos-latest
        node: 18
      - os: ubuntu-latest
        node: 14
```

- 5 jobs

### P124 : Dada la siguiente configuración, ¿cuántos trabajos ejecutará GitHub Actions cuando se evalúe esta matriz?

```yaml
strategy:
  matrix:
    os: [ubuntu-latest, windows-latest]
    node: [14, 16]
    include:
      - os: macos-latest
        node: 18
      - os: ubuntu-latest
        node: 14
```

- 5 trabajos

### Recurso de estudio

[Running variations of jobs in a workflow - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/running-variations-of-jobs-in-a-workflow#expanding-or-adding-matrix-configurations)

## Question 125

### **Q125: At what levels can environment variables be defined ? (Choose three)**

- Job level
- Workflow level
- Step level

### **P125 : ¿En qué niveles se pueden definir las variables de entorno? (Elija tres)**

- Nivel de trabajo
- Nivel de flujo de trabajo
- Nivel de paso

### Recurso de estudio

[Store information in variables - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables)

## Question 126

### **Q126: How should a dependent job reference the `output1` value produced by a job named `job1` earlier in the same workflow?**

- ${{needs.job1.outputs.output1}}

### **P126: ¿Cómo debería un trabajo dependiente hacer referencia al `output1`valor producido por un trabajo nombrado `job1`anteriormente en el mismo flujo de trabajo?**

- ${{needs.job1.outputs.output1}}

### Recurso de estudio

[Passing information between jobs - Documentación de GitHub](https://docs.github.com/es/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/passing-information-between-jobs)f
