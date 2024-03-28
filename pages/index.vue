<template>
  <div>
    <h1>1Xercise</h1>    
  </div>
</template>

<script lang="ts" setup>
  import type { Workout } from '~/types/workout';
  import { useStorageAvailable } from '~/composables/storageAvailable';

  const router = useRouter();

  onMounted(() => {

    const unsavedId = (() => {
      // check if localStorage is avaialble, otherwise set the id to null
      if (useStorageAvailable('localStorage')) {
        const unsavedWorkoutString = localStorage.getItem('unsavedWorkout')
        if (unsavedWorkoutString) {
          try {
            const unsavedWorkout: Workout = JSON.parse(unsavedWorkoutString)
            return unsavedWorkout?.id
          } catch (e) {
            console.error('Error parsing unsaved workout: ', e)
          }
        }
      } else {
        console.error('Local Storage is not available')
      }
      return null
    })()

    if (unsavedId) {
        router.push(`/workouts/${unsavedId}`);
    } else {
      router.push('/workouts')
    }
  })
</script>