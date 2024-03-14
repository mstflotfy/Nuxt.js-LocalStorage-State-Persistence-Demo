<template>
  <div>
    <header>
      <nav>
        <button @click="$router.back">Back</button>
      </nav>
      <h1>Workout {{ workout.id }}</h1>  
    </header>
    <main>
      <form aria-label="Workout Info">
        <h2>Workout Info</h2>
        <label for="name">Workout Name </label>
        <input 
          id="name" 
          type="text" 
          placeholder="Enter Workout Name"
          v-model="workout.name"
          aria-label="Workout Name"
          aria-required="true"
        />
        <br>
        <br>
        <label for="workoutDate">Workout Date </label>
        <input 
          id="workoutDate" 
          type="date" 
          v-model="workout.date"
          aria-label="Workout Date"
          aria-required="true"
        />
      </form>
    </main>
  </div>
</template>

<script lang="ts" setup>
  import type { Workout } from '~/types/workout';

  const route = useRoute();
  const localStorageAvailable = ref(false)

  const workout = ref<Workout>({
    id: route.params.id as string,
    name: '',
    date: new Date().toISOString().slice(0, 10)
  })

  watch(workout, (newWorkout) => {
    if (localStorageAvailable.value) {
      localStorage.setItem('unsavedWorkout', JSON.stringify(newWorkout))
    }
  }, { deep: true })

  onMounted(() => {

    // Check if localStorage is avaialable
    localStorageAvailable.value = (() => {
      if (useStorageAvailable('localStorage')) {
        return true
      } else {
        console.error('...')
        return false
      }
    })()

    // Load from localStorage
    if (localStorageAvailable.value) {
      const unsavedWorkoutString = localStorage.getItem('unsavedWorkout') 
      if (unsavedWorkoutString) {
        try {
          workout.value = JSON.parse(unsavedWorkoutString)
        } catch (e) {
          console.error('...')
        }
      }
    }
  })  

  onBeforeRouteLeave(() => {
    // Reset localStorage
    if (localStorageAvailable.value) {
      localStorage.removeItem('unsavedWorkout')
    }
  })
</script>