<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>7 Sinais Silenciosos da Tireoide</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cream: #F7F4EF;
    --sage: #4A6B5B;
    --sage-light: #E8F0EC;
    --sage-mid: #7A9E8E;
    --dark: #1C2820;
    --warm-gray: #8A8478;
    --accent: #C4956A;
    --accent-light: #F5EDE2;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--dark);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* HERO */
  .hero {
    position: relative;
    padding: 3rem 1.5rem 2.5rem;
    background: var(--dark);
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 260px; height: 260px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(74,107,91,0.35) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: -40px;
    width: 180px; height: 180px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(196,149,106,0.2) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-eyebrow {
    display: inline-block;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--sage-mid);
    border: 1px solid rgba(122,158,142,0.4);
    padding: 5px 14px;
    border-radius: 40px;
    margin-bottom: 1.5rem;
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 7vw, 2.6rem);
    font-weight: 600;
    line-height: 1.2;
    color: #fff;
    margin-bottom: 0.75rem;
  }

  .hero h1 em {
    font-style: italic;
    color: var(--accent);
  }

  .hero-sub {
    font-size: 15px;
    font-weight: 300;
    color: rgba(255,255,255,0.6);
    line-height: 1.6;
    margin-bottom: 2rem;
    max-width: 380px;
  }

  .hero-cta {
    display: inline-block;
    background: var(--sage);
    color: #fff;
    font-size: 14px;
    font-weight: 500;
    padding: 14px 28px;
    border-radius: 50px;
    text-decoration: none;
    letter-spacing: 0.02em;
    transition: background 0.2s, transform 0.15s;
  }

  .hero-cta:hover { background: #3a5748; transform: translateY(-1px); }

  .hero-note {
    margin-top: 1rem;
    font-size: 12px;
    color: rgba(255,255,255,0.35);
    letter-spacing: 0.03em;
  }

  /* PROMISE STRIP */
  .strip {
    background: var(--sage);
    padding: 1.1rem 1.5rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .strip-icon {
    width: 32px; height: 32px;
    background: rgba(255,255,255,0.12);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 15px;
  }

  .strip p { font-size: 13px; color: rgba(255,255,255,0.9); line-height: 1.5; }
  .strip strong { color: #fff; }

  /* SECTION */
  section { padding: 2.5rem 1.5rem; }

  .section-label {
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--sage);
    margin-bottom: 0.5rem;
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 600;
    line-height: 1.3;
    color: var(--dark);
    margin-bottom: 0.5rem;
  }

  .section-title em { font-style: italic; color: var(--sage); }

  .section-desc {
    font-size: 14px;
    color: var(--warm-gray);
    line-height: 1.7;
    margin-bottom: 1.75rem;
  }

  /* SINAIS */
  .sinais { display: flex; flex-direction: column; gap: 1rem; }

  .sinal {
    background: #fff;
    border-radius: 16px;
    padding: 1.1rem 1.25rem;
    display: flex;
    align-items: flex-start;
    gap: 14px;
    border: 1px solid rgba(0,0,0,0.05);
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s ease, transform 0.5s ease;
  }

  .sinal.visible { opacity: 1; transform: none; }

  .sinal-num {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: var(--sage-light);
    color: var(--sage);
    font-size: 13px;
    font-weight: 500;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }

  .sinal-num.special {
    background: var(--accent-light);
    color: var(--accent);
  }

  .sinal h3 {
    font-size: 14px;
    font-weight: 500;
    color: var(--dark);
    margin-bottom: 3px;
  }

  .sinal p {
    font-size: 13px;
    color: var(--warm-gray);
    line-height: 1.55;
  }

  .sinal.highlight {
    background: var(--dark);
    border-color: transparent;
  }

  .sinal.highlight h3 { color: #fff; }
  .sinal.highlight p  { color: rgba(255,255,255,0.6); }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(0,0,0,0.08), transparent);
    margin: 0 1.5rem;
  }

  /* PROOF */
  .proof { background: var(--sage-light); }

  .proof-card {
    background: #fff;
    border-radius: 16px;
    padding: 1.25rem;
    border: 1px solid rgba(74,107,91,0.15);
    margin-bottom: 1rem;
  }

  .stars { color: var(--accent); font-size: 14px; margin-bottom: 8px; }
  .proof-text { font-size: 14px; color: var(--dark); line-height: 1.65; margin-bottom: 10px; font-family: 'Playfair Display', serif; font-style: italic; }
  .proof-author { font-size: 12px; color: var(--warm-gray); font-weight: 500; letter-spacing: 0.04em; }

  /* WHAT YOU GET */
  .gets { display: flex; flex-direction: column; gap: 0.75rem; }

  .get-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 0.9rem 1rem;
    background: #fff;
    border-radius: 12px;
    border: 1px solid rgba(0,0,0,0.05);
  }

  .get-icon {
    width: 32px; height: 32px;
    background: var(--sage-light);
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 16px;
  }

  .get-item h4 { font-size: 13px; font-weight: 500; color: var(--dark); margin-bottom: 2px; }
  .get-item p  { font-size: 12px; color: var(--warm-gray); line-height: 1.5; }

  /* CTA SECTION */
  .cta-section {
    background: var(--dark);
    padding: 3rem 1.5rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cta-section::before {
    content: '';
    position: absolute;
    top: -80px; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(74,107,91,0.25) 0%, transparent 70%);
    pointer-events: none;
  }

  .cta-section h2 {
    font-family: 'Playfair Display', serif;
    font-size: 1.75rem;
    font-weight: 600;
    color: #fff;
    line-height: 1.3;
    margin-bottom: 0.75rem;
  }

  .cta-section h2 em { font-style: italic; color: var(--accent); }

  .cta-section p {
    font-size: 14px;
    color: rgba(255,255,255,0.55);
    margin-bottom: 2rem;
    line-height: 1.6;
  }

  .cta-big {
    display: block;
    background: var(--sage);
    color: #fff;
    font-size: 15px;
    font-weight: 500;
    padding: 16px 32px;
    border-radius: 50px;
    text-decoration: none;
    letter-spacing: 0.02em;
    margin-bottom: 1rem;
    transition: background 0.2s, transform 0.15s;
  }

  .cta-big:hover { background: #3a5748; transform: translateY(-2px); }

  .cta-safe {
    font-size: 11px;
    color: rgba(255,255,255,0.3);
    letter-spacing: 0.04em;
  }

  /* FOOTER */
  footer {
    padding: 1.5rem;
    text-align: center;
    font-size: 11px;
    color: var(--warm-gray);
    border-top: 1px solid rgba(0,0,0,0.06);
  }

  /* PULSE ANIMATION */
  @keyframes pulse-border {
    0%, 100% { box-shadow: 0 0 0 0 rgba(74,107,91,0.3); }
    50%       { box-shadow: 0 0 0 8px rgba(74,107,91,0); }
  }

  .cta-big { animation: pulse-border 2.5s ease infinite; }
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <div class="hero-eyebrow">Guia gratuito · Saúde hormonal</div>
  <h1>Os <em>7 sinais</em> que sua tireoide está pedindo socorro</h1>
  <p class="hero-sub">Descubra por que você se sente cansada, travada e sem resultado — mesmo fazendo tudo certo.</p>
  <a href="#cta" class="hero-cta">Quero o guia gratuito →</a>
  <p class="hero-note">100% gratuito · Sem compromisso</p>
</section>

<!-- STRIP -->
<div class="strip">
  <div class="strip-icon">⚡</div>
  <p><strong>Mais de 3.200 mulheres</strong> já identificaram o problema real com esse guia.</p>
</div>

<!-- SINAIS -->
<section>
  <p class="section-label">O que você vai descobrir</p>
  <h2 class="section-title">Os 7 sinais <em>silenciosos</em></h2>
  <p class="section-desc">A tireoide sobrecarregada raramente aparece em exames comuns. Mas ela manda sinais claros no corpo — que a maioria ignora ou trata separado.</p>

  <div class="sinais">

    <div class="sinal">
      <div class="sinal-num">1</div>
      <div>
        <h3>Cansaço que não passa com sono</h3>
        <p>Você dorme 8h e acorda esgotada. Não é preguiça — pode ser metabolismo travado.</p>
      </div>
    </div>

    <div class="sinal">
      <div class="sinal-num">2</div>
      <div>
        <h3>Cabelo caindo mais do que o normal</h3>
        <p>Queda difusa, sem calvície — sinal clássico de hipotireoidismo subclínico.</p>
      </div>
    </div>

    <div class="sinal">
      <div class="sinal-num">3</div>
      <div>
        <h3>Dificuldade de emagrecer com dieta</h3>
        <p>Você corta calorias, faz exercício e a balança não move. A tireoide pode estar travando seu metabolismo.</p>
      </div>
    </div>

    <div class="sinal">
      <div class="sinal-num">4</div>
      <div>
        <h3>Frio o tempo todo — mesmo no verão</h3>
        <p>Sensação de frio constante nas extremidades é um dos primeiros sinais hormonais.</p>
      </div>
    </div>

    <div class="sinal">
      <div class="sinal-num">5</div>
      <div>
        <h3>Intestino preso com frequência</h3>
        <p>A tireoide regula o trânsito intestinal. Quando ela trava, o intestino trava junto.</p>
      </div>
    </div>

    <div class="sinal">
      <div class="sinal-num">6</div>
      <div>
        <h3>Humor instável e ansiedade sem causa</h3>
        <p>Mudanças de humor, irritabilidade e névoa mental podem ser 100% hormonais.</p>
      </div>
    </div>

    <div class="sinal highlight">
      <div class="sinal-num special">7</div>
      <div>
        <h3>O sinal que aparece no seu rosto 👁</h3>
        <p>Esse é o mais ignorado — e o primeiro a aparecer antes de qualquer exame dar alterado. Revelado no guia completo.</p>
      </div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- WHAT YOU GET -->
<section>
  <p class="section-label">O que está no guia</p>
  <h2 class="section-title">Tudo que você recebe <em>grátis</em></h2>
  <p class="section-desc">Um material criado para quem já tentou de tudo e ainda não encontrou a causa raiz.</p>

  <div class="gets">
    <div class="get-item">
      <div class="get-icon">📋</div>
      <div>
        <h4>Os 7 sinais explicados em detalhes</h4>
        <p>O que cada sintoma indica e como ele se conecta à função tireoidiana.</p>
      </div>
    </div>
    <div class="get-item">
      <div class="get-icon">🔬</div>
      <div>
        <h4>Quais exames pedir ao médico</h4>
        <p>TSH normal não significa tireoide saudável. Veja o painel completo que você precisa solicitar.</p>
      </div>
    </div>
    <div class="get-item">
      <div class="get-icon">🥗</div>
      <div>
        <h4>3 alimentos que sabotam a tireoide</h4>
        <p>Itens considerados saudáveis que bloqueiam a absorção hormonal — e que você provavelmente come todo dia.</p>
      </div>
    </div>
    <div class="get-item">
      <div class="get-icon">✅</div>
      <div>
        <h4>Checklist de autoavaliação</h4>
        <p>Responda 10 perguntas e descubra seu nível de alerta hormonal em menos de 2 minutos.</p>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- PROOF -->
<section class="proof">
  <p class="section-label">Quem já leu</p>
  <h2 class="section-title" style="margin-bottom:1.25rem">Resultados <em>reais</em></h2>

  <div class="proof-card">
    <div class="stars">★★★★★</div>
    <p class="proof-text">"Fiz o checklist e marquei 6 de 7. Levei para a minha endocrinologista e ela pediu os exames que estavam faltando. Finalmente descobri o que estava errado."</p>
    <p class="proof-author">— Fernanda R., 38 anos · Belo Horizonte</p>
  </div>

  <div class="proof-card">
    <div class="stars">★★★★★</div>
    <p class="proof-text">"Eu achava que era só estresse. Depois de ler o guia percebi que era exatamente o sinal 7 que eu tinha há meses sem saber o que era."</p>
    <p class="proof-author">— Juliana M., 44 anos · São Paulo</p>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="cta">
  <h2>Baixe agora e descubra <em>o que está te travando</em></h2>
  <p>Gratuito. Sem cadastro longo. Você recebe o guia completo agora.</p>
  <a href="#" class="cta-big">Quero o guia gratuito agora →</a>
  <p class="cta-safe">🔒 Seus dados estão seguros · Sem spam</p>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 · Conteúdo informativo. Não substitui avaliação médica profissional.</p>
</footer>

<script>
  const sinais = document.querySelectorAll('.sinal');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.15 });
  sinais.forEach(s => obs.observe(s));
</script>

</body>
</html>
