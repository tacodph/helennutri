<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import { ArrowUpRight, Globe, MessageCircle } from 'lucide-vue-next';

const whatsapp = 'https://wa.me/5561992098384?text=' + encodeURIComponent('Olá, Helen! Quero agendar minha consulta nutricional.');
</script>

<template>
    <Head title="Links | Helen Freitas Nutricionista">
        <meta name="description" content="Conheça os projetos da nutricionista Helen Freitas, participe do Desafio da Virada e agende sua consulta pelo WhatsApp." />
        <meta property="og:title" content="Helen Freitas | Nutrição e cuidado com você" />
        <meta property="og:description" content="Desafio da Virada, agendamento de consultas e todos os links da nutri." />
    </Head>

    <main class="bio-page">
        <div class="bio-shell">
            <header class="portrait">
                <img class="portrait-photo" src="/images/helen-consultorio.png" alt="Helen Freitas em seu consultório" fetchpriority="high" width="1600" height="2400" />
                <div class="portrait-shade" aria-hidden="true"></div>
                <a class="instagram" href="https://www.instagram.com/helenfreitasnutri/" target="_blank" rel="noopener noreferrer" aria-label="Instagram da Helen Freitas (abre em nova aba)">
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true"><rect x="2" y="2" width="20" height="20" rx="5" /><circle cx="12" cy="12" r="4" /><circle cx="18" cy="6" r="1" fill="currentColor" stroke="none" /></svg>
                </a>
                <div class="portrait-copy">
                    <p class="eyebrow">NUTRIÇÃO COM PROPÓSITO</p>
                    <h1>Helen Freitas<span>.</span></h1>
                    <p class="profession">Nutricionista</p>
                    <p class="intro">Seu próximo passo para uma vida<br />mais leve começa aqui.</p>
                </div>
            </header>

            <div class="links-content">
                <Link href="/" class="site-link">
                    <Globe :size="19" aria-hidden="true" />
                    <span>Conheça meu site</span>
                    <ArrowUpRight :size="20" aria-hidden="true" />
                </Link>

                <section aria-labelledby="projects-title" class="projects">
                    <div class="section-heading">
                        <span class="eyebrow">ESCOLHA SEU PRÓXIMO PASSO</span>
                        <h2 id="projects-title">Vamos juntas?</h2>
                        <p>Conheça meus projetos e cuide de você.</p>
                    </div>

                    <a class="project-card challenge" href="https://www.desafio30firme.com.br/" target="_blank" rel="noopener noreferrer">
                        <div class="card-content">
                            <span class="card-label">9 NOV → 8 DEZ · 30 DIAS</span>
                            <h3>Desafio da Virada</h3>
                            <p class="challenge-headline"><span>30 dias.</span><br />5 objetivos.</p>
                            <p>Não espere o momento perfeito para começar sua transformação.</p>
                            <span class="card-action">Quem topa? <ArrowUpRight :size="18" aria-hidden="true" /></span>
                        </div>
                    </a>

                    <a class="project-card appointment" :href="whatsapp" target="_blank" rel="noopener noreferrer">
                        <img class="appointment-photo" src="/images/helen-agendamento.png" alt="Helen Freitas sorrindo, sentada no sofá com uma xícara" width="1599" height="778" loading="lazy" />
                        <div class="appointment-copy">
                            <span class="card-label">SEU MOMENTO DE CUIDADO</span>
                            <h3>Vamos cuidar<br />de você?</h3>
                            <p>Uma alimentação que faz sentido para sua rotina. Dê o primeiro passo e agende sua consulta comigo.</p>
                            <span class="appointment-cta"><MessageCircle :size="19" aria-hidden="true" /> Agendar pelo WhatsApp <ArrowUpRight :size="18" aria-hidden="true" /></span>
                        </div>
                    </a>
                </section>

                <footer>
                    <img class="footer-logo" src="/logo_fundo_escuro.png" alt="Helen Freitas" width="381" height="86" loading="lazy" />
                    <p>Nutrição de verdade. Cuidado com você.</p>
                    <small>© {{ new Date().getFullYear() }} Helen Freitas. Todos os direitos reservados.</small>
                </footer>
            </div>
        </div>
    </main>
</template>

<style scoped>
.bio-page { min-height: 100vh; background: #eee7eb; color: #30232d; padding: 40px 20px; font-family: 'Instrument Sans', sans-serif; }
.bio-shell { max-width: 540px; margin: auto; background: #faf7f8; overflow: hidden; border-radius: 24px; box-shadow: 0 20px 80px #45283c14; }
.portrait { height: 460px; position: relative; background: #3b2034; }
.portrait-photo { width: 100%; height: 100%; object-fit: cover; object-position: center 32%; }
.portrait-shade { position: absolute; inset: 0; background: linear-gradient(180deg, #2513220a 20%, #25132240 46%, #251322f5 100%); }
.instagram { position: absolute; top: 24px; right: 24px; border: 1px solid #ffffff70; border-radius: 50%; width: 42px; height: 42px; display: grid; place-items: center; color: white; background: #2b17282b; }
.portrait-copy { position: absolute; bottom: 32px; left: 32px; color: #fff; }
.eyebrow { font-size: 10px; font-weight: 700; letter-spacing: .18em; }
.portrait-copy .eyebrow { color: #f0bbdf; margin-bottom: 10px; }
h1 { font-size: clamp(36px, 8vw, 46px); font-weight: 600; letter-spacing: -.055em; line-height: 1.1; }
h1 span { color: #df80c4; }
.profession { color: #edc8e2; font-size: 14px; margin-top: 5px; }
.intro { font-size: 14px; line-height: 1.6; color: #f3e8ef; margin-top: 16px; }
.links-content { padding: 24px 28px 28px; }
.site-link { display: flex; align-items: center; gap: 12px; background: #fff; padding: 17px 20px; border: 1px solid #e4d7e0; border-radius: 12px; font-size: 14px; font-weight: 600; }
.site-link span { flex: 1; }
.site-link svg { color: #9c2b85; }
.section-heading { margin: 32px 0 20px; text-align: center; }
.section-heading .eyebrow { color: #9c2b85; }
h2 { font-size: 28px; font-weight: 600; letter-spacing: -.04em; margin: 7px 0; }
.section-heading p { font-size: 13px; color: #776b74; }
.project-card { display: block; position: relative; overflow: hidden; border-radius: 16px; transition: transform .2s, box-shadow .2s; }
.challenge { background: #131210; color: #f5f2ec; padding: 24px; border: 1px solid #332d20; }
.card-content { position: relative; z-index: 1; }
.card-label { display: flex; align-items: center; gap: 7px; font-size: 9px; font-weight: 700; letter-spacing: .14em; }
.challenge .card-label { color: #ffb619; }
.challenge h3 { font-size: 21px; line-height: 1.2; font-weight: 900; font-style: italic; text-transform: uppercase; letter-spacing: -.04em; margin: 18px 0 10px; }
.challenge p { font-size: 13px; line-height: 1.6; color: #c9c3b8; max-width: 310px; }
.challenge .challenge-headline { font-family: Impact, 'Arial Narrow', sans-serif; font-size: clamp(38px, 10vw, 52px); line-height: 1.05; font-weight: 900; font-style: italic; text-transform: uppercase; letter-spacing: -.025em; color: #f5f2ec; margin-bottom: 18px; }
.challenge-headline span { color: #f8ac18; }
.card-action { display: inline-flex; align-items: center; gap: 26px; font-size: 13px; font-weight: 800; margin-top: 22px; padding: 13px 22px; border-radius: 999px; background: #f8ac18; color: #131210; }
.appointment { margin-top: 18px; background: #f1e8e3; border: 1px solid #e5d8cf; }
.appointment-photo { display: block; width: 100%; height: auto; aspect-ratio: 1599 / 778; object-fit: cover; }
.appointment-copy { padding: 26px; }
.appointment .card-label { color: #805f70; font-size: 9px; }
.appointment h3 { font-family: Georgia, serif; font-size: clamp(32px, 8vw, 40px); line-height: 1.1; font-weight: 400; letter-spacing: -.04em; margin: 12px 0 16px; color: #4c3041; }
.appointment p { font-size: 13px; line-height: 1.7; color: #725e68; max-width: 340px; }
.appointment-cta { display: flex; align-items: center; justify-content: center; gap: 10px; margin-top: 23px; padding: 16px 12px; border-radius: 999px; background: #9c2b85; color: #fff; font-size: 13px; font-weight: 600; }
footer { text-align: center; margin-top: 34px; color: #83737e; font-size: 11px; }
.footer-logo { display: block; width: 230px; max-width: 100%; height: auto; margin: 0 auto 14px; }
footer nav { display: flex; justify-content: center; gap: 10px; margin: 18px 0 12px; }
footer small { font-size: 9px; }
a:focus-visible { outline: 3px solid #b44b9e; outline-offset: 4px; }
@media (hover: hover) { .project-card:hover { transform: translateY(-3px); box-shadow: 0 10px 25px #5928491a; } .site-link:hover { border-color: #9c2b85; } }
@media (max-width: 580px) { .bio-page { padding: 0; background: #faf7f8; } .bio-shell { border-radius: 0; box-shadow: none; } .portrait { height: 430px; } .portrait-copy { left: 26px; bottom: 28px; } .links-content { padding: 22px; } }
@media (max-width: 360px) { .links-content { padding: 18px; } .appointment-copy { padding: 22px 18px; } .appointment-cta { gap: 7px; font-size: 12px; } .challenge { padding: 20px; } }
@media (prefers-reduced-motion: reduce) { .project-card { transition: none; } }
</style>
