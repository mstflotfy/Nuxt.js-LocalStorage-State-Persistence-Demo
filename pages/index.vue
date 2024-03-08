<template>
  <div>
    <h1>1Xercise</h1>    
  </div>
</template>

<script lang="ts" setup>
  const router = useRouter();

  onMounted(() => {
    const unsavedId = localStorage.getItem('unsavedId') ?? ''

    if (unsavedId) {
        router.push(`/workouts/${unsavedId}`);
    } else {
      router.push('/workouts')
    }
  })
</script>