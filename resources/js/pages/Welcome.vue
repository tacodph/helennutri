<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import { ref, onMounted, onUnmounted } from 'vue';
import { ArrowDown as ArrowDownIcon, ChevronDown as ChevronDownIcon } from 'lucide-vue-next';
import { MessageSquare, FileText, CheckCircle } from 'lucide-vue-next';
import { type CSSProperties } from 'vue';

const testimonials = [
  {
    name: "Diego Fernando",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "Excelente trabalho! Nutriçao simples, sem terrorismo, com comida de verdade! Atendeu a mim e minha esposa, conseguimos atingir nossas metas de perda de peso e o mais importante, manter o peso por ser uma dieta sustentável! Preço justo pelo trabalho desempenhado! Recomendamos a todos!",
    rating: 5,
    result: "8kg perdidos"
  },
 {
    name: "Douver Barros",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "A melhor nutri que eu poderia ter. Não inventa modinha, é assertiva e monta todo um cardápio que faz sentido para a minha realidade. Existe um eu antes e depois desse acompanhamento. Meu abdômen sempre foi um calcanhar de Aquiles, e consegui feitos absurdos com a dieta dela. Hoje já tiro a camisa sem medo de ser feliz. Ah, e o atendimento em si tbm é excelente. Super alto astral. Recomendo demais.",
    rating: 5,
    result: "8kg perdidos"
  },
  {
    name: "Natalia Alves",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "Sempre tive resistência com nutricionista, tive algumas experiências frustradas, infelizmente. E confesso que a Hellen tirou todas essas más impressões. Profissional comprometida com uma dieta saudável e acessível para o paciente. Sem firula, jogo limpo com o corpo e com a pessoa!",
    rating: 5,
    result: "8kg perdidos"
  },
    {
    name: "Karen Santana Victorino",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "Excelente nutricionista! As consultas são muito esclarecedoras, esclarece todas as dúvidas, o plano alimentar é de acordo com a individualidade de cada um.  Profissional muito atenciosa e querida!",
    rating: 5,
    result: "8kg perdidos"
  },
    {
    name: "Raquel  Lucia",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "Não é apenas mais uma nutricionista aplicando fórmulas de déficit calórico, além de super competente, é uma profissional humana que nos enxerga para além do peso. Melhor decisão da vida!",
    rating: 5,
    result: "8kg perdidos"
  },
    {
    name: "Ana Lucia Paula Alvarenga",
    age: 28,
    role: "Designer",
    url: "/images/helen/depoimentos/thumb.png",
    content: "Recomendo!! A Helen é uma nutricionista competente, educada, as dicas de receitas são excelentes ,ela nos conduz à realização de uma dieta alimentar mais saudável, visando alcançar nossos objetivos pessoais.",
    rating: 5,
    result: "8kg perdidos"
  },

];

const faqs = ref([
  {
    question: "Qual é a diferença entre os planos?",
    answer: "A principal diferença está na frequência e duração do acompanhamento. O Plano Mensal é para quem deseja começar e entender Sobre  um plano alimentar personalizado.</br> O Plano Semanal é um acompanhamento intensivo de curto prazo. </br> O Plano Trimestral oferece suporte contínuo durante 3 meses, com consultas quinzenais.",
    isOpen: false
  },
  {
    question: "Posso começar com um plano e depois mudar para outro?",
    answer: "Sim! Se durante o acompanhamento você sentir necessidade de um suporte mais frequente ou quiser prolongar o acompanhamento, basta conversar diretamente comigo para ajustarmos o plano ideal para você.",
    isOpen: false
  },
  {
    question: "O que acontece se eu não puder comparecer a uma consulta?",
    answer: "Entendo que imprevistos acontecem. Se precisar remarcar, pedimos que avise com no mínimo 24 horas de antecedência para reagendarmos sem custos. Cancelamentos de última hora podem ser considerados como consulta realizada.",
    isOpen: false
  },
  {
    question: "As consultas online têm a mesma eficácia das presenciais?",
    answer: "Sim! O atendimento online é estruturado para oferecer a mesma qualidade e atenção que o presencial. Toda a avaliação nutricional, orientação alimentar, ajustes e suporte são realizados de forma segura e eficaz.",
    isOpen: false
  },
  {
    question: "Quais são as formas de pagamento aceitas?",
    answer: "Aceito pagamentos via Pix e cartão de crédito. Para planos de maior valor, é possível parcelar em até 6 vezes no cartão (com acréscimo das taxas da operadora).",
    isOpen: false
  },
  {
    question: "Vou receber suporte fora das consultas?",
    answer: "O aplicativo DIETBOX dispõe de chat para retirar dúvidas, materiais de apoio, orientações específicas para você, metas e o diário alimentar que é um grande aliado para acompanhar sua adesão ao plano alimentar. Porem é durante as consultas que as dúvidas são esclarecidas com mais especificidade e precisão.",
    isOpen: false
    },
  {
    question: "Preciso ter algum material ou exames para a primeira consulta?",
    answer: "Se tiver exames laboratoriais recentes (até 6 meses), é interessante trazer. Caso não tenha, podemos iniciar normalmente e, se necessário, solicitarei posteriormente.",
    isOpen: false
  },
  {
    question: "Os resultados são garantidos?",
    answer: "O acompanhamento é personalizado para te orientar da melhor maneira possível. Os resultados dependem da sua dedicação e da aplicação prática das estratégias passadas. Meu compromisso é te guiar para que o processo seja o mais leve e eficaz possível.",
    isOpen: false
  },

]);

const steps = [
  {
    icon: MessageSquare,
    title: "Cada pessoa é única, e seu caminho para a saúde também.",
    description:
      "Meu trabalho começa com uma avaliação completa da sua saúde, rotina e objetivos, para criar um plano nutricional totalmente personalizado.",
    color: "primary",
  },
  {
    icon: FileText,
    title: "Acompanhamento próximo e humanizado.",
    description:
      "Mudar hábitos pode ser desafiador, mas você não estará sozinho. Além da orientação nutricional, ofereço suporte emocional e educacional, ajustando o plano conforme suas necessidades.",
    color: "secondary",
  },
  {
    icon: CheckCircle,
    title: "Foco em resultados duradouros.",
    description:
      "Vai muito além de seguir uma dieta, meu objetivo é a mudança real e sustentável do seu estilo de vida, melhorando sua relação com a comida e pensando sempre em resultados sustentáveis e duradouros.",
    color: "accent",
  },
];

const beneficios = [
  "leve,  realista e eficaz",
];

const currentText = ref('');
const currentIndex = ref(0);

let disposed = false;
onUnmounted(() => { disposed = true; });

const typeText = async () => {
  if (disposed) return;
  const text = beneficios[currentIndex.value];

  // Limpa o texto atual
  currentText.value = '';

  // Anima cada letra
  for (let i = 0; i < text.length && !disposed; i++) {
    currentText.value += text[i];
    await new Promise(resolve => setTimeout(resolve, 100)); // Velocidade da digitação
  }

  // Espera um pouco antes de apagar
  await new Promise(resolve => setTimeout(resolve, 2000));

  // Anima apagando
  while (currentText.value.length > 0 && !disposed) {
    currentText.value = currentText.value.slice(0, -1);
    await new Promise(resolve => setTimeout(resolve, 50)); // Velocidade do apagar
  }

  // Próxima palavra
  currentIndex.value = (currentIndex.value + 1) % beneficios.length;

  // Continua o ciclo após um pequeno delay
  await new Promise(resolve => setTimeout(resolve, 500));
  typeText();
};

onMounted(() => {
  typeText();
});

// Animation styles
const testimonialContainer: CSSProperties = {
  width: '100%',
  maxWidth: '100vw',
  position: 'relative',
  overflow: 'hidden',
};

const testimonialTrack: CSSProperties = {
  display: 'flex',
  gap: '24px',
  padding: '20px 0',
};

const testimonialCard: CSSProperties = {
  flex: '0 0 350px',
};
</script>

<template>
  <Head title="Helen Freitas - Nutricionista" />

  <div class="helen-welcome min-h-screen bg-white text-gray-800 overflow-x-hidden">
    <!-- Header -->
    <header class="fixed top-0 w-full z-50 bg-white/90 backdrop-blur-lg border-b border-gray-200">
      <div class="container mx-auto px-4 py-4">
        <div class="flex items-center justify-between">
          <!-- Logo -->
          <div class="flex items-center gap-3">
            <img src="/logo_fundo_escuro.png" alt="Helen Freitas Nutricionista" class="h-10" />
          </div>

          <!-- Navigation -->
          <nav class="hidden md:flex items-center gap-8">
            <a href="#como-funciona" class="text-gray-800 hover:text-verde-primario transition-colors">
              Sobre
            </a>
            <a href="#depoimentos" class="text-gray-800 hover:text-verde-primario transition-colors">
              Depoimentos
            </a>
            <a href="#precos" class="text-gray-800 hover:text-verde-primario transition-colors">
              Planos
            </a>
            <a href="#faq" class="text-gray-800 hover:text-verde-primario transition-colors">
              Perguntas Frequentes
            </a>
          </nav>


        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="pt-24 pb-16 px-4 relative overflow-hidden mt-10 min-h-[800px] md:min-h-[1000px]">
      <!-- Background Image - Mobile -->
      <div
        class="md:hidden absolute inset-0 z-3 bg-cover bg-no-repeat bg-right"
        style="background-image: url('/images/helen/fitness_model_female_800.png'); background-position: top -100px center;"
      >
        <div class="absolute inset-0 bg-gradient-to-r from-white/80 via-white/50 to-white/30"></div>
      </div>

      <!-- Background Image - Desktop -->
      <div
        class="hidden md:block absolute inset-0 z-3 bg-cover bg-no-repeat bg-right"
        style="background-image: url('/images/helen/fitness_model_female_800.png'); background-position: top -500px right 0;"
      >
        <div class="absolute inset-0 bg-gradient-to-r from-white/80 via-white/50 to-white/30"></div>
      </div>

      <!-- Background Effects -->
      <div class="absolute inset-0 bg-gradient-to-br from-verde-primario/10 via-transparent to-roxo/10 z-[1]"></div>
      <div class="absolute top-20 left-10 w-64 h-64 bg-verde-primario/20 rounded-full blur-3xl z-[1]"></div>
      <div class="absolute bottom-20 right-10 w-96 h-96 bg-turquesa/20 rounded-full blur-3xl z-[1]"></div>

      <div class="container mx-auto relative z-10">

        <div class="max-w-4xl text-left">
          <!-- Main Headline -->
          <h1 class="text-4xl md:text-6xl font-bold mb-6 leading-tight">
            <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text">
              Você merece um
            </span>
            <br />
            <span class="text-gray-800">acompanhamento nutricional</span>
            <br />
            <span class="text-verde-primario">{{ currentText }}</span>
            <span class="animate-blink">|</span>
          </h1>

          <!-- Subtitle
          <p class="text-xl md:text-2xl text-gray-700 mb-10 max-w-3xl leading-relaxed">
            Alimentação personalizada, criada por uma especialista, <br>
            sempre ao alcance do seu bolso.
          </p>
-->
          <!-- CTA Buttons -->
          <div class="flex flex-col sm:flex-row gap-4 justify-start mb-16">
            <a class="rounded-full bg-verde-primario px-8 py-4 text-lg font-semibold text-white hover:bg-verde-primario/90 transition-colors animate-glow"
                href="https://wa.me/5561992098384?text=Quero%20agendar%20a%20minha%20consulta!" target="_blank" rel="noopener nofollow">
                                Saiba mais
            </a>

          </div>

          <!-- Trust Indicators -->
          <div class="flex flex-col sm:flex-row items-start justify-start gap-8 text-sm text-gray-600">
            <div class="flex items-center gap-2">
              <div class="w-2 h-2 bg-verde-primario rounded-full"></div>
              <span>Sem terrorismo nutricional. </span>
            </div>
            <div class="flex items-center gap-2">
              <div class="w-2 h-2 bg-turquesa rounded-full"></div>
              <span>Sem modismos. </span>
            </div>
            <div class="flex items-center gap-2">
              <div class="w-2 h-2 bg-roxo rounded-full"></div>
              <span>Com resultados reais.</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Scroll Indicator -->
      <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 animate-bounce">
        <ArrowDownIcon class="w-6 h-6 text-verde-primario" />
      </div>
    </section>


<!-- Black Friday -->
    <section class="px-4 py-6">
      <div class="max-w-3xl mx-auto rounded-2xl bg-black border border-verde-primario/50 p-5 shadow-lg shadow-verde-primario/10 flex flex-col md:flex-row md:items-center md:justify-between gap-4">
        <div>
          <span class="inline-block rounded-full border-2 border-verde-primario px-4 py-0.5 text-lg font-extrabold text-verde-primario">BLACK</span>
          <p class="mt-3 text-lg md:text-xl font-bold text-white">3 consultas online + plano alimentar individualizado</p>
        </div>
        <a
          class="shrink-0 inline-flex items-center justify-center gap-2 rounded-full bg-verde-primario px-6 py-3 font-semibold text-white hover:bg-verde-primario/90 transition-colors"
          href="https://wa.me/5561992098384?text=Quero%20saber%20mais%20sobre%20a%20oferta%20Black!"
          target="_blank"
          rel="noopener nofollow"
        >
          Saiba mais <span aria-hidden="true">→</span>
        </a>
      </div>
    </section>

<!-- Chegou a hora de cuidar de você!  -->
    <section id="como-funciona" class="relative py-20 px-4 overflow-hidden">
      <!-- Background Images with Overlay -->
      <div class="absolute inset-0 z-0">
        <!-- Female Image -->
        <div class="absolute top-0 left-0 w-full md:w-1/2 h-1/2 md:h-full">
          <img
            src="/images/helen/fitness_model_female_800.png"
            alt="Fitness Results"
            class="w-full h-full object-cover"
          />
          <div class="absolute inset-0 bg-gradient-to-b md:bg-gradient-to-tl from-white/90 md:from-white/100 via-white/80 to-transparent"></div>
        </div>
        <!-- Male Image -->
        <div class="absolute bottom-0 right-0 w-full md:w-1/2 h-1/2 md:h-full">
          <img
            src="/images/helen/fitness_model_male2_crop.png"
            alt="Fitness Results"
            class="w-full h-full object-cover"
          />
          <div class="absolute inset-0 bg-gradient-to-t md:bg-gradient-to-tr from-white/90 md:from-white/100 via-white/80 to-transparent"></div>
        </div>
        <!-- Center fade overlay -->
        <div class="absolute inset-0">
          <div class="absolute inset-y-0 left-1/2 transform -translate-x-1/2 w-32 bg-gradient-to-r from-transparent via-white/50 to-transparent"></div>
          <div class="absolute inset-x-0 top-1/2 transform -translate-y-1/2 h-32 md:hidden bg-gradient-to-b from-transparent via-white/50 to-transparent"></div>
        </div>
        <!-- Additional overlay for text readability -->
        <div class="absolute inset-0 bg-white/40"></div>
      </div>

      <div class="container mx-auto relative z-10">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gray-800">
            Chegou a hora de <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text uppercase">cuidar de você!</span>
          </h2>
          <p class="text-xl text-gray-700 max-w-2xl mx-auto">
            Transforme sua relação com a comida e com o seu corpo!
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto cen">
          <div
            v-for="(step, index) in steps"
            :key="index"
            class="relative group"
          >
            <!-- Connection Line -->
            <div
              v-if="index < steps.length - 1"
              class="hidden md:block absolute top-16 left-full w-full h-0.5 bg-gradient-to-r from-verde-primario to-turquesa opacity-30 z-0"
            ></div>

            <!-- Step Card -->
            <div class="relative z-10 bg-white backdrop-blur-sm rounded-2xl p-8 text-center border border-gray-200 hover:border-verde-primario/50 transition-all duration-300 hover:-translate-y-2 group-hover:shadow-2xl group-hover:shadow-verde-primario/20">
              <!-- Step Number -->
              <div class="absolute -top-4 left-1/2 transform -translate-x-1/2 w-8 h-8 bg-verde-primario rounded-full flex items-center justify-center text-white font-bold text-sm shadow-lg">
                {{ index + 1 }}
              </div>

              <!-- Icon -->
              <div
                class="w-16 h-16 mx-auto mb-6 rounded-2xl flex items-center justify-center"
                :class="{
                  'bg-verde-primario/20': step.color === 'primary',
                  'bg-turquesa/20': step.color === 'secondary',
                  'bg-roxo/20': step.color === 'accent'
                }"
              >
                <component
                  :is="step.icon"
                  class="w-8 h-8"
                  :class="{
                    'text-verde-primario': step.color === 'primary',
                    'text-turquesa': step.color === 'secondary',
                    'text-roxo': step.color === 'accent'
                  }"
                />
              </div>

              <!-- Content -->
              <h3 class="text-xl font-semibold mb-4 text-gray-800">
                {{ step.title }}
              </h3>
              <p class="text-gray-700 leading-relaxed">
                {{ step.description }}
              </p>
            </div>
          </div>
        </div>

        <p class="mt-4 text-center text-sm text-gray-700 ">
           Nutrição personalizada, com cuidado humano e foco em resultados reais e duradouros.
        </p>


        <!-- Bottom CTA -->
        <div class="text-center mt-16">
          <div class="inline-flex items-center gap-2 bg-verde-primario/10 px-6 py-3 rounded-full border border-verde-primario/30">
            <div class="w-2 h-2 bg-verde-primario rounded-full animate-pulse"></div>
            <span class="text-verde-primario font-medium">Acompanhamento 100% personalizado</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Sobre o Nutricionista -->
    <section id="como-funciona" class="relative py-20 px-4 overflow-hidden">
      <!-- Background Images with Overlay -->
      <div class="absolute inset-0 z-0">
        <!-- Female Image -->
        <div class="absolute top-0 left-0 w-full md:w-1/2 h-1/2 md:h-full">
            <div class="text-center mb-16">

        </div>
        <h2 class="text-4xl md:text-5xl font-bold mb-6">

            </h2>

          <div class="absolute inset-0 bg-gradient-to-b md:bg-gradient-to-tl from-white/90 md:from-white/100 via-white/80 to-transparent"></div>
        </div>
        <!-- Male Image -->
        <div class="absolute bottom-0 right-0 w-full md:w-1/2 h-1/2 md:h-full">
          <img
            src="/images/helen/grupo_amigos_expanded.png"
            alt="Fitness Results"
            class="w-full h-full object-cover"
          />
          <div class="absolute inset-0 bg-gradient-to-t md:bg-gradient-to-tr from-white/90 md:from-white/100 via-white/80 to-transparent"></div>
        </div>
        <!-- Center fade overlay -->
        <div class="absolute inset-0">
          <div class="absolute inset-y-0 left-1/2 transform -translate-x-1/2 w-32 bg-gradient-to-r from-transparent via-white/50 to-transparent"></div>
          <div class="absolute inset-x-0 top-1/2 transform -translate-y-1/2 h-32 md:hidden bg-gradient-to-b from-transparent via-white/50 to-transparent"></div>
        </div>
        <!-- Additional overlay for text readability -->
        <div class="absolute inset-0 bg-white/40"></div>
      </div>

      <div class="container mx-auto relative z-10">
        <div class="mb-16">
          <h3 class="text-left text-4xl md:text-5xl font-bold mb-6 text-gray-800">
            Olá, sou <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text uppercase">Helen Freitas,</span>
            <br />
            nutricionista há mais de 10 anos. <br />
            Mas a verdade é que nem sempre  <br />
            tive uma relação saudável com a comida.
          </h3>

              <p class="text-xl text-gray-700 max-w-2xl text-justify" >

            </p>
            <br />
             <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                  Antes de encontrar o equilíbrio entre comer saudável e gostar do meu corpo, eu também vivi a luta contra a balança.<br />
                    Passei por diversas dietas restritivas, desenvolvi compulsão alimentar e senti, na pele, a frustração de começar e desistir várias vezes.
                </p>
                <br />
                <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                    Foi essa vivência que transformou a minha forma de cuidar.<br />
                    Desde o início da minha carreira, optei por não usar somente a técnica, mas uma escuta ativa de quem já viveu a  experiência de estar do lado de lá.
                    </p>
                    <br />
                    <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                    Ser a profissional que acolhe e caminha junto!.<br />
                    Porque eu sei que essa jornada vai muito além de “força de vontade”.
                    </p>

                    <br />

                    <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                                    Regras rígidas só afastam.<br />
                      A nutrição precisa ser vista como um estilo de vida que caiba na sua realidade.<br />
                      E é isso que constrói resultado de verdade.

                     </p>
                     <br />

                    <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                                    Meu compromisso é com você. <br />
                        É em encontrar uma estratégia nutricional que faça sentido na sua vida — realista, respeitosa e duradoura.

                     </p>
                     <br />

                    <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                               Se você está cansada de recomeçar,talvez você só precise de um caminho diferente.

                     </p>
                     <br />

                    <p class="text-xl text-gray-700 max-w-2xl text-justify" >
                                    E ele pode começar aqui.

                     </p>

        </div>




        <!-- Bottom CTA -->
        <div class="text-center mt-16">
          <div class="inline-flex items-center gap-2 bg-verde-primario/10 px-6 py-3 rounded-full border border-verde-primario/30">
            <div class="w-2 h-2 bg-verde-primario rounded-full animate-pulse"></div>
            <span class="text-verde-primario font-medium">Acompanhamento nutricional humano, realista e duradouro.</span>
          </div>
        </div>
      </div>
    </section>


    <!-- Testimonials -->
    <section id="depoimentos" class="py-20 px-4 bg-gray-50 overflow-hidden">
      <div class="container mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gray-800">
            Resultados <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text">reais</span> de pessoas reais
          </h2>
          <p class="text-xl text-gray-700 max-w-2xl mx-auto">
            Nada melhor do que ouvir quem já passou pela experiência de transformação. Veja o que algumas pacientes dizem
          </p>
        </div>

        <div id="testimonials" :style="testimonialContainer" class="overflow-hidden">
          <!-- Testimonials Track -->
          <div class="relative overflow-hidden">
            <div :style="testimonialTrack" class="pb-4 testimonial-marquee">
              <div
                v-for="(testimonial, index) in [...testimonials, ...testimonials]"
                :key="index"
                :style="testimonialCard"
                class="bg-white hover:bg-gray-50 rounded-xl border border-gray-200 p-6 hover:border-verde-primario/50 transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-verde-primario/20"
              >
                <!-- Rating -->
                <div class="flex mb-4 text-lg">
                  <template v-for="star in 5" :key="star">
                    <span :class="star <= testimonial.rating ? 'text-verde-primario' : 'text-gray-300'">★</span>
                  </template>
                </div>

                <!-- Content -->

                <p class="text-gray-700 mb-6 leading-relaxed text-sm">
                  "{{ testimonial.content }}"
                </p>

                <!-- Result Badge -->
                 <!--
                <div class="mb-4">
                  <span class="inline-block bg-verde-primario/20 text-verde-primario px-3 py-1 rounded-full text-xs font-medium">
                    {{ testimonial.result }}
                  </span>
                </div>
              -->
                <!-- Author -->
                <div class="flex items-center gap-3">

                  <!--
                   <div class="w-10 h-10 rounded-full bg-turquesa/20 flex items-center justify-center">
                    <img
                      :src="testimonial.url"
                      :alt="testimonial.name"
                      class="w-10 h-10 rounded-full object-cover"
                    />
                    </div>
                    -->

                  <div>
                    <h4 class="font-semibold text-gray-800 text-sm">
                      {{ testimonial.name }}
                    </h4>
                    <!--
                    <p class="text-gray-600 text-xs">
                      {{ testimonial.role }}, {{ testimonial.age }} anos
                    </p>
                  -->
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Social Proof -->
        <div class="text-center mt-16">
          <div class="inline-flex items-center gap-6 bg-white px-8 py-4 rounded-2xl border border-gray-200 shadow-lg">
            <div class="text-center">
              <div class="text-2xl font-bold text-verde-primario">6k+</div>
              <div class="text-sm text-gray-600">Seguidores</div>
            </div>
            <div class="w-px h-8 bg-gray-300"></div>
            <div class="text-center">
              <div class="text-2xl font-bold text-turquesa">4.9★</div>
              <div class="text-sm text-gray-600">Avaliação média</div>
            </div>
            <div class="w-px h-8 bg-gray-300"></div>
            <div class="text-center">
              <div class="text-2xl font-bold text-roxo">95%</div>
              <div class="text-sm text-gray-600">Taxa de sucesso</div>
            </div>
          </div>
        </div>
      </div>
    </section>




    <!-- Comparison -->
    <section id="precos" class="py-20 px-4">
      <div class="container mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gray-800">
            <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text">Qual o seu momento?</span> Escolha seu plano ideal:
          </h2>
          <p class="text-xl text-gray-700 max-w-2xl mx-auto">

          </p>
        </div>


        <!-- Pricing Card -->
        <div class="max-w-4xl mx-auto">
          <div class="grid md:grid-cols-2 gap-6">

            <!-- Plano Trimestral -->
            <div class="bg-white border border-gray-200 hover:border-verde-primario/50 rounded-xl pt-12 px-8 pb-8 text-center relative overflow-visible transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-verde-primario/20 grid grid-rows-[auto_1fr_auto] h-full">

              <!-- Header -->
              <div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Plano Online -  8 semanas</h3>


                <!-- Pricing -->
                <div class="mb-6">

                </div>
              </div>

              <!-- Features -->
              <div>
                <ul class="space-y-3 mb-8 text-left">
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">4 consultas online (1 inicial + 3 retornos ao longo de 8 semanas)</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Consulta inicial completa com investigação de hábitos, rotina e objetivos</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Orientação para fotos e medidas corporais para acompanhamento da evolução</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Ajustes estratégicos a cada encontro, conforme adesão e dificuldades</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Plano alimentar adaptado à sua rotina e realidade</span>
                  </li>
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800"> Acompanhamento próximo, mesmo à distância</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800"> Educação nutricional para autonomia</span>
                  </li>
                </ul>
              </div>

              <!-- Footer -->
              <div>
                <a class="block w-full bg-white border-2 border-verde-primario text-verde-primario hover:bg-verde-primario hover:text-white font-semibold py-4 rounded-full mb-4 transition-colors" href="https://wa.me/5561992098384?text=Gostaria%20de%20mais%20informações%20sobre%20o%20Plano%20Online" target="_blank" rel="noopener nofollow">
                    Saiba mais
            </a>

                <p class="text-xs text-gray-600">
                  Agende sua consulta
                </p>
              </div>
            </div>



            <!-- Plano Semanal -->

            <div class="bg-gradient-to-b from-white to-gray-50 border border-verde-primario/50 rounded-xl pt-12 px-8 pb-8 text-center relative overflow-visible grid grid-rows-[auto_1fr_auto] h-full">


              <!-- Header -->
              <div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Plano Semanal</h3>


                <!-- Pricing -->
                <div class="mb-6">

                </div>
              </div>

             <!-- Features -->
              <div>
                <ul class="space-y-3 mb-8 text-left">
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">5 consultas presenciais em 4 semanas</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Uma vez por semana</span>
                  </li>

                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Novo cardápio e ajustes semanais</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Lista de compras e metas para o retorno</span>
                  </li>
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Acompanhamento com foto comparativa</span>
                  </li>
                </ul>
              </div>

              <!-- Footer -->
              <div>
                <a class="block w-full bg-white border-2 border-verde-primario text-verde-primario hover:bg-verde-primario hover:text-white font-semibold py-4 rounded-full mb-4 transition-colors" href="https://wa.me/5561992098384?text=Gostaria%20de%20mais%20informações%20sobre%20o%20Plano%20Semanal" target="_blank" rel="noopener nofollow">
                    Saiba mais
                </a>

                <p class="text-xs text-gray-600">
                  Agende sua consulta
                </p>
              </div>
            </div>
          </div>
        </div>



        <!-- Pricing Card -->
        <div class="max-w-4xl mx-auto mt-13">
          <div class="grid md:grid-cols-2 gap-6">
            <!-- Plano Trimestral -->
            <div class="bg-white border border-gray-200 hover:border-verde-primario/50 rounded-xl pt-12 px-8 pb-8 text-center relative overflow-visible transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-verde-primario/20 grid grid-rows-[auto_1fr_auto] h-full">
              <!-- Popular badge -->
              <div class="absolute -top-4 left-1/2 transform -translate-x-1/2 bg-verde-primario text-white px-6 py-2 rounded-full text-sm font-semibold">
                Mais Popular
              </div>
              <!-- Header -->
              <div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Plano Trimestral</h3>


                <!-- Pricing -->
                <div class="mb-6">

                </div>
              </div>

              <!-- Features -->
              <div>
                <ul class="space-y-3 mb-8 text-left">
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">1 Encontro a cada 15 dias</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">3 presenciais + 3 online (De forma intercalada)</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Avaliação física em todas as consultas presenciais</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Ajustes de dieta a cada 15 dias</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Lista de compras e metas personalizadas</span>
                  </li>
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Acompanhamento de evolução com fotos comparativas</span>
                  </li>
                </ul>
              </div>

              <!-- Footer -->
              <div>
                <a class="block w-full bg-white border-2 border-verde-primario text-verde-primario hover:bg-verde-primario hover:text-white font-semibold py-4 rounded-full mb-4 transition-colors" href="https://wa.me/5561992098384?text=Gostaria%20de%20mais%20informações%20sobre%20o%20Plano%20Trimestral" target="_blank" rel="noopener nofollow">
                    Saiba mais
            </a>

                <p class="text-xs text-gray-600">
                  Agende sua consulta
                </p>
              </div>
            </div>

            <!-- Plano Básico -->
            <div class="bg-white border border-gray-200 hover:border-verde-primario/50 rounded-xl pt-12 px-8 pb-8 text-center relative overflow-visible transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-verde-primario/20 grid grid-rows-[auto_1fr_auto] h-full">
              <!-- Flexible badge -->
               <!--
              <div class="absolute -top-4 left-1/2 transform -translate-x-1/2 bg-gray-300 text-gray-800 px-6 py-2 rounded-full text-sm font-semibold">
                Mais Flexível
              </div>
-->
              <!-- Header -->
              <div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Plano Básico</h3>


                <!-- Pricing -->
                <div class="mb-6">

                </div>
              </div>

              <!-- Features -->
              <div>
                <ul class="space-y-3 mb-8 text-left">
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">1 consulta + 1 retorno em até 30 dias</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Presencial</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Avaliação física completa</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Plano alimentar calculado para o seu objetivo</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Lista de compras e metas para o retorno</span>
                  </li>
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-700">Foto comparativa</span>
                  </li>
                </ul>
              </div>

              <!-- Footer -->
              <div>
                <a class="block w-full bg-white border-2 border-verde-primario text-verde-primario hover:bg-verde-primario hover:text-white font-semibold py-4 rounded-full mb-4 transition-colors" href="https://wa.me/5561992098384?text=Gostaria%20de%20mais%20informações%20sobre%20o%20Plano%20Básico" target="_blank" rel="noopener nofollow">
                    Saiba mais
            </a>

                <p class="text-xs text-gray-600">
                  Agende sua consulta
                </p>
              </div>
            </div>

            <!-- Plano Semestral (oculto: altere v-if para true para exibir novamente) -->
            <div v-if="false" class="bg-white border border-gray-200 hover:border-verde-primario/50 rounded-xl pt-12 px-8 pb-8 text-center relative overflow-visible transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-verde-primario/20 grid grid-rows-[auto_1fr_auto] h-full">
              <!-- Flexible badge -->
               <!--
              <div class="absolute -top-4 left-1/2 transform -translate-x-1/2 bg-gray-300 text-white px-6 py-2 rounded-full text-sm font-semibold">
                Mais Flexível
              </div>
-->
              <!-- Header -->
              <div>
                <h3 class="text-2xl font-bold text-gray-800 mb-2">Plano Semestral</h3>


                <!-- Pricing -->
                <div class="mb-6">

                </div>
              </div>

             <!-- Features -->
              <div>
                <ul class="space-y-3 mb-8 text-left">
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">6 consultas mensais presenciais (1 Presencial por mês)</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Avaliação física completa em todas as consultas</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Estratégias práticas para alimentação na rotina</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Plano alimentar adaptado a imprevistos e vida real</span>
                  </li>
                  <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Acompanhamento próximo e personalizado</span>
                  </li>
                   <li class="flex items-center gap-3">
                    <span class="text-verde-primario w-5 h-5 flex-shrink-0">✓</span>
                    <span class="text-gray-800">Educação nutricional para autonomia</span>
                  </li>
                </ul>
              </div>

              <!-- Footer -->
              <div>
            <a class="block w-full bg-white border-2 border-verde-primario text-verde-primario hover:bg-verde-primario hover:text-white font-semibold py-4 rounded-full mb-4 transition-colors" href="https://wa.me/5561992098384?text=Gostaria%20de%20mais%20informações%20sobre%20o%20Plano%20Semestral" target="_blank" rel="noopener nofollow">
                    Saiba mais
            </a>
                <p class="text-xs text-gray-600">
                  Agende sua consulta
                </p>
              </div>
            </div>
          </div>
        </div>

          <!-- Money Back Guarantee -->
          <div class="text-center mt-12">
            <div class="inline-flex items-center gap-3 bg-verde-primario/10 px-6 py-3 rounded-full border border-verde-primario/30">
              <div class="w-8 h-8 rounded-full bg-verde-primario flex items-center justify-center">
                <span class="text-white">✓</span>
              </div>
              <span class="text-verde-primario font-medium">
                Seu momento é agora
              </span>
            </div>
          </div>
          <!-- Money Back Guarantee -->
      </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="py-20 px-4 bg-gray-50 relative">

      <div class="container mx-auto relative z-10">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 text-gray-800">
            Perguntas <span class="bg-gradient-to-r from-verde-primario to-turquesa text-transparent bg-clip-text">Frequentes</span>
          </h2>
          <p class="text-xl text-gray-700 max-w-2xl mx-auto">
            Tudo que você precisa saber sobre a consulta e o plano
          </p>
        </div>

        <div class="max-w-3xl mx-auto">
          <div class="space-y-4">
            <div
              v-for="(faq, index) in faqs"
              :key="index"
              class="bg-gray-100 border border-gray-200 rounded-lg overflow-hidden transition-all duration-300 hover:border-verde-primario/50"
            >
              <button
                @click="faq.isOpen = !faq.isOpen"
                class="w-full px-6 py-6 text-left flex items-center justify-between hover:text-verde-primario transition-colors group"
              >
                <span class="font-semibold text-gray-800 group-hover:text-verde-primario group-hover:underline transition-all duration-300 group-hover:underline-offset-4">{{ faq.question }}</span>
                <span
                  class="transform transition-transform duration-300"
                  :class="{ 'rotate-180': faq.isOpen }"
                >
                  <ChevronDownIcon   n class="w-6 h-6" />
                </span>
              </button>
              <div
                v-show="faq.isOpen"
                class="px-6 pb-6 text-gray-700 leading-relaxed"
              >
                {{ faq.answer }}
              </div>
            </div>
          </div>
        </div>





      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-50 py-16 px-4">
      <div class="container mx-auto">
        <!-- Main Footer Content -->
        <div class="grid md:grid-cols-4 gap-8 mb-12">
          <!-- Logo and Description -->
          <div class="md:col-span-1">
            <div class="mb-4">
              <img src="/logo_fundo_escuro.png" alt="Helen Freitas Nutricionista" class="h-8" />
            </div>
            <p class="text-gray-700 leading-relaxed mb-6">
              Está pronta para transformar sua alimentação e sua relação com a comida?
            </p>
            <!-- Social Media -->
            <div class="flex gap-4">
              <a href="https://www.instagram.com/helenfreitasnutri/" class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center text-verde-primario hover:bg-verde-primario hover:text-white transition-colors">
                <span class="text-sm font-bold">@</span>
              </a>

            </div>
          </div>

          <!-- Product Links -->
          <div>
            <h3 class="font-semibold text-gray-800 mb-4">Produto</h3>
            <ul class="space-y-3">
              <li><a href="#como-funciona" class="text-gray-700 hover:text-verde-primario transition-colors">Sobre </a></li>
              <li><a href="#depoimentos" class="text-gray-700 hover:text-verde-primario transition-colors">Depoimentos</a></li>
              <li><a href="#precos" class="text-gray-700 hover:text-verde-primario transition-colors">Planos</a></li>
            </ul>
          </div>

          <!-- Support Links -->
          <div>
            <h3 class="font-semibold text-gray-800 mb-4">Suporte</h3>
            <ul class="space-y-3">
              <li><a href="#faq" class="text-gray-700 hover:text-verde-primario transition-colors">Perguntas Frequentes</a></li>

            </ul>
          </div>

        </div>

        <!-- Bottom Section -->
        <div class="border-t border-gray-200 pt-8">
          <div class="flex flex-col md:flex-row justify-between items-center gap-4">
            <p class="text-gray-700 text-sm">
              © {{ new Date().getFullYear() }} Helen Freitas. Todos os direitos reservados.
            </p>
            <div class="flex items-center gap-6 text-sm">
              <span class="text-gray-700">🇧🇷 Feito no Brasil</span>
              <div class="flex items-center gap-2">
                <div class="w-2 h-2 bg-verde-primario rounded-full animate-pulse"></div>
                <span class="text-verde-primario">Todos os sistemas operacionais</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
    </div>
</template>

<style scoped>
.testimonial-marquee { width: max-content; animation: testimonials-scroll 100s linear infinite; }
.testimonial-marquee:hover, .testimonial-marquee:focus-within { animation-play-state: paused; }
@keyframes testimonials-scroll { to { transform: translateX(-50%); } }
@media (prefers-reduced-motion: reduce) { .testimonial-marquee { animation: none; } }

html {
  scroll-behavior: smooth;
}

.animate-blink {
  animation: blink 1s step-end infinite;
  display: inline-block;
  margin-left: 1px;
  font-weight: 300;
}

@keyframes blink {
  from, to {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

.animate-fade-in {
  animation: fadeIn 0.5s ease-out forwards;
  opacity: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.thin-scrollbar {
  scrollbar-width: thin;
  scrollbar-color: #E2E8F0 transparent;
  padding-right: 6px;
}

.thin-scrollbar::-webkit-scrollbar {
  width: 6px;
}

.thin-scrollbar::-webkit-scrollbar-track {
  background: transparent;
}

.thin-scrollbar::-webkit-scrollbar-thumb {
  background-color: #E2E8F0;
  border-radius: 3px;
}

.thin-scrollbar::-webkit-scrollbar-thumb:hover {
  background-color: #CBD5E1;
}

#testimonials ::-webkit-scrollbar {
  height: 5px;
  width: 5px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
}

#testimonials ::-webkit-scrollbar-thumb {
  background: var(--verde-primario);
  border-radius: 4px;
}

#testimonials ::-webkit-scrollbar-corner {
  background: rgba(255, 255, 255, 0.1);
}

.helen-welcome {
  font-family: 'Instrument Sans', sans-serif;
  --verde-primario: #9c2b85;
}

</style>
