<template>
  <div class="min-h-screen bg-gradient-to-b from-pink-100 to-rose-200 font-sans">
    <!-- Tela 1 -->
    <div v-if="step === 1" class="h-screen flex flex-col items-center justify-center px-4">
      <h1 class="text-4xl text-rose-600 font-bold mb-4 animate-pulse">Feliz Dia dos Pais!</h1>
      <p class="text-center text-rose-700 mb-8">
        Pai Marcilio, preparei esta surpresa para você ver no seu Xiaomi.
      </p>
      <button
        @click="step = 2"
        class="bg-rose-500 hover:bg-rose-600 text-white p-6 rounded-full shadow-lg transition-all duration-300 transform hover:scale-110"
      >
        <span class="text-2xl">Ver lembranças ❤️</span>
      </button>
    </div>

    <!-- Tela 2 -->
    <div v-if="step === 2" class="h-screen flex flex-col items-center px-4 py-8 max-w-md mx-auto">
      <h2 class="text-3xl text-rose-700 font-bold mb-4">Nossas lembranças</h2>

      <div class="aspect-[9/16] w-full mb-6 rounded-xl overflow-hidden shadow-xl">
        <img
          :src="photos[currentIndex].src"
          class="w-full h-full object-cover"
          :alt="photos[currentIndex].caption"
        />
      </div>

      <div class="bg-white/80 rounded-xl p-6 mb-6 shadow-md">
        <p class="text-lg text-rose-800 leading-relaxed text-center">
          {{ photos[currentIndex].caption }}
        </p>
      </div>

      <div class="flex gap-4">
        <button
          v-if="currentIndex > 0"
          @click="currentIndex--"
          class="bg-rose-500 hover:bg-rose-600 text-white px-4 py-2 rounded-full transition-all duration-300"
        >
          Anterior
        </button>
        <button
          v-if="currentIndex < photos.length - 1"
          @click="currentIndex++"
          class="bg-rose-600 hover:bg-rose-700 text-white px-4 py-2 rounded-full transition-all duration-300"
        >
          Próximo
        </button>
        <button
          v-else
          @click="step = 3"
          class="bg-rose-600 hover:bg-rose-700 text-white px-4 py-2 rounded-full transition-all duration-300"
        >
          Mensagem final
        </button>
      </div>
    </div>

    <!-- Tela 3 -->
    <div v-if="step === 3" class="h-screen flex flex-col items-center justify-center text-center px-4">
      <h2 class="text-4xl text-rose-700 font-bold mb-6">Feliz Dia dos Pais!</h2>
      <div class="animate-love text-5xl space-x-2 mb-4">
        <span class="text-rose-600 animate-bounce">T</span>
        <span class="text-rose-700 animate-bounce delay-100">E</span>
        <span class="text-rose-800 animate-bounce delay-200">A</span>
        <span class="text-rose-900 animate-bounce delay-300">M</span>
        <span class="text-rose-950 animate-bounce delay-400">O</span>
      </div>
      <p class="text-xl text-rose-800 animate-pulse">
        Pai Marcilio, com amor do seu filho Marcilio.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      step: 1,
      currentIndex: 0,
      photos: [
        { src: 'https://source.unsplash.com/600x900/?father,baby&sig=1', caption: 'Quando eu ainda era seu pequeno tesouro.' },
        { src: 'https://source.unsplash.com/600x900/?father,child&sig=2', caption: 'Nossos passeios no parque.' },
        { src: 'https://source.unsplash.com/600x900/?father,kid&sig=3', caption: 'Você me ensinando a andar de bicicleta.' },
        { src: 'https://source.unsplash.com/600x900/?father,son&sig=4', caption: 'Primeiro dia de aula, você ao meu lado.' },
        { src: 'https://source.unsplash.com/600x900/?father,family&sig=5', caption: 'As férias cheias de aventuras.' },
        { src: 'https://source.unsplash.com/600x900/?father,teen&sig=6', caption: 'Na adolescência, sempre com seus conselhos.' },
        { src: 'https://source.unsplash.com/600x900/?father,graduation&sig=7', caption: 'Sua alegria na minha formatura.' },
        { src: 'https://source.unsplash.com/600x900/?father,man&sig=8', caption: 'Nossas conversas de homem para homem.' },
        { src: 'https://source.unsplash.com/600x900/?father,sunrise&sig=9', caption: 'Planejando o futuro juntos.' },
        { src: 'https://source.unsplash.com/600x900/?father,son&sig=10', caption: 'Hoje, adulto, sigo aprendendo com você.' }
      ]
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

.animate-love span {
  animation: love 1s ease-out forwards;
  display: inline-block;
  margin: 0 5px;
}

.delay-100 { animation-delay: 0.2s; }
.delay-200 { animation-delay: 0.4s; }
.delay-300 { animation-delay: 0.6s; }
.delay-400 { animation-delay: 0.8s; }
</style>
