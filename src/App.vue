<template>
  <div class="min-h-screen bg-gradient-to-b from-pink-100 to-rose-200 font-sans">
    <!-- Tela 1 -->
    <div v-if="step === 1" class="h-screen flex flex-col items-center justify-center px-4">
      <h1 class="text-4xl text-rose-600 font-bold mb-8 animate-pulse">Bem vinda meu amor!</h1>
      <button 
        @click="step = 2"
        class="bg-rose-500 hover:bg-rose-600 text-white p-6 rounded-full shadow-lg transition-all duration-300 transform hover:scale-110"
      >
        <span class="text-2xl">Clique aqui ❤️</span>
      </button>
    </div>

    <!-- Tela 2 -->
    <div v-if="step === 2" class="h-screen flex flex-col items-center px-4 py-8 max-w-md mx-auto">
      <h2 class="text-3xl text-rose-700 font-bold mb-4">Pra você meu amor</h2>
      
      <div class="aspect-[9/16] w-full mb-6 rounded-xl overflow-hidden shadow-xl">
        <img 
          src="./assets/camila.jpeg" 
          class="w-full h-full object-cover"
          alt="Nossa foto"
        >
      </div>

      <div class="bg-white/80 rounded-xl p-6 mb-6 shadow-md">
        <p class="text-lg text-rose-800 leading-relaxed text-center">
          Você é a mulher mais especial da minha vida! ❤️<br>
          Hoje, quero reforçar o quanto você é incrível
          guerreira, estudiosa, companheira e meu maior motivo de continuar tentando.<br>
          Sou apaixonado por todo momentinho que passamos juntos,
          sou feliz mais que tudo por ter você na minha vida <br>
          Te amo mais que tudo, minha princesa
        </p>
      </div>

      <button
        @click="step = 3"
        class="bg-rose-600 hover:bg-rose-700 text-white px-8 py-3 rounded-full transition-all duration-300 transform hover:scale-105"
      >
        Tchauzinho 👋
      </button>
    </div>

    <!-- Tela 3 -->
    <div v-if="step === 3" class="h-screen flex items-center justify-center">
      <div class="text-center">
        <div class="animate-love text-6xl space-y-4">
          <div class="text-rose-600 animate-bounce">T</div>
          <div class="text-rose-750 animate-bounce delay-100">E</div>
          <div class="text-rose-800 animate-bounce delay-200">A</div>
          <div class="text-rose-850 animate-bounce delay-300">S</div>
          <div class="text-rose-900 animate-bounce delay-400">M</div>
          <div class="text-rose-950 animate-bounce delay-100">O</div>
        </div>
        <p class="mt-8 text-xl text-rose-700 animate-pulse">Abacatezinha</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      step: 1
    }
  }
}
</script>

<style>
@keyframes love {
  0% { opacity: 0; transform: scale(0.3); }
  50% { transform: scale(1.2); }
  100% { opacity: 1; transform: scale(1); }
}

.animate-love div {
  animation: love 1s ease-out forwards;
  display: inline-block;
  margin: 0 5px;
}

.delay-100 { animation-delay: 0.2s; }
.delay-200 { animation-delay: 0.4s; }
.delay-300 { animation-delay: 0.6s; }
.delay-400 { animation-delay: 0.8s; }
</style>
