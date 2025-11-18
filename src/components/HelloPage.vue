<template>
  <div class="hello-page">
    <h1>{{ greeting }}</h1>
    <p class="subtitle">Welcome to your Vue 3 application!</p>
    <div class="info">
      <p>This is a simple Hello page built with Vue 3 and Vite.</p>
      <p>Current time: {{ currentTime }}</p>
    </div>
    <button @click="updateGreeting" class="btn">Change Greeting</button>

    <div class="dashboard-container">
      <h2>Dashboard</h2>
      <iframe
        src="https://vizuro.embed-omniapp.co/dashboards/ded18b78"
        class="dashboard-iframe"
        frameborder="0"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
  name: 'HelloPage',
  setup() {
    const greeting = ref('Hello, World!')
    const currentTime = ref('')
    const greetings = [
      'Hello, World!',
      'Welcome!',
      'Greetings!',
      'Hi there!',
      'Good to see you!'
    ]

    const updateGreeting = () => {
      const randomIndex = Math.floor(Math.random() * greetings.length)
      greeting.value = greetings[randomIndex]
    }

    const updateTime = () => {
      currentTime.value = new Date().toLocaleTimeString()
    }

    onMounted(() => {
      updateTime()
      setInterval(updateTime, 1000)
    })

    return {
      greeting,
      currentTime,
      updateGreeting
    }
  }
}
</script>

<style scoped>
.hello-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

h1 {
  color: #42b983;
  font-size: 3rem;
  margin-bottom: 1rem;
  animation: fadeIn 1s ease-in;
}

.subtitle {
  font-size: 1.5rem;
  color: #666;
  margin-bottom: 2rem;
}

.info {
  background-color: #f5f5f5;
  border-radius: 8px;
  padding: 1.5rem;
  margin: 2rem 0;
}

.info p {
  margin: 0.5rem 0;
  color: #333;
}

.btn {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 1rem;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn:hover {
  background-color: #35a372;
}

.btn:active {
  transform: scale(0.98);
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.dashboard-container {
  margin-top: 3rem;
  width: 100%;
}

.dashboard-container h2 {
  color: #2c3e50;
  font-size: 2rem;
  margin-bottom: 1.5rem;
}

.dashboard-iframe {
  width: 100%;
  height: 600px;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
</style>
