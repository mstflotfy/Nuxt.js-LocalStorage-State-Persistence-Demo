<template>
  <div>
    <header>
      <nav>
        <button @click="$router.back">Back</button>
      </nav>
      <h1>Workout {{ workoutId }}</h1>  
    </header>
    <main>
      <form>
        <h2>Workout Info</h2>
        <label for="name">Workout Name </label>
        <input 
          id="name" 
          type="text" 
          placeholder="Enter Workout Name"
          v-model="workoutName"
        />
        <br>
        <br>
        <label for="workoutDate">Workout Date </label>
        <input 
          id="workoutDate" 
          type="date" 
          v-model="workoutDate"
        />
      </form>
    </main>
  </div>
</template>

<script lang="ts" setup>
  const route = useRoute();
  const workoutId = route.params.id
  const workoutName = ref('')
  const workoutDate = ref(new Date().toISOString().slice(0,10))


  // Save to localStorage
  watch([workoutName, workoutDate], ([newName, newDate], [oldName, oldDate]) => {
        localStorage.setItem('unsavedWorkoutName', newName)
        localStorage.setItem('unsavedWorkoutDate', newDate)
        localStorage.setItem('unsavedId', workoutId as string)
  })

  onMounted(() => {
    // Load from localStorage
    const unsavedId = localStorage.getItem('unsavedId') ?? ''
    const unsavedName = localStorage.getItem('unsavedWorkoutName') ?? ''
    const unsavedDate = localStorage.getItem('unsavedWorkoutDate') ?? ''
    if (unsavedId) {
        if (unsavedName) workoutName.value = unsavedName
        if (unsavedDate) workoutDate.value = unsavedDate
    }
  })  

  onBeforeRouteLeave(() => {
    // Reset localStorage
    localStorage.removeItem('unsavedId')
    localStorage.removeItem('unsavedWorkoutName')
    localStorage.removeItem('unsavedWorkoutDate')
  })
</script>