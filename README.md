
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>ENIAC • Marcos Vínicius</title>

<style>
  /* ===============================
     Variáveis e Reset
  ================================== */
  :root {
    color-scheme: dark;
    --black: #030303;
    --black-soft: #0b0b0b;
    --card: #111111;
    --text: #f7f7f7;
    --muted: #c5c5c5;
    --accent: #ff1e56;
    --accent-dark: #9d0026;
    --border: rgba(255, 30, 86, 0.35);
  }
  * {
    box-sizing: border-box;
  }

  /* ===============================
     Estrutura global
  ================================== */
  body {
    margin: 0;
    font-family: "Inter", "Segoe UI", system-ui, sans-serif;
    background: radial-gradient(circle at top, #191919 0%, var(--black) 55%);
    color: var(--text);
    min-height: 100vh;
    padding: clamp(1rem, 3vw, 2.5rem);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  main {
    width: min(1200px, 100%);
    padding: clamp(1.5rem, 4vw, 3.5rem);
    border-radius: 34px;
    background: linear-gradient(145deg, rgba(0,0,0,0.95), rgba(5,5,5,0.85));
    border: 1px solid rgba(255, 30, 86, 0.25);
    box-shadow: 0 40px 120px rgba(0,0,0,0.8), 0 0 90px rgba(255, 30, 86, 0.15);
  }
  section + section {
    margin-top: 2.75rem;
  }
  h1, h2, h3 {
    margin: 0;
    letter-spacing: 0.05em;
  }
  h1 {
    font-size: clamp(2.6rem, 5vw, 4rem);
    text-transform: uppercase;
  }
  h2 {
    font-size: clamp(1.6rem, 3vw, 2.3rem);
    color: var(--accent);
    margin-bottom: 1rem;
  }
  p {
    margin: 0;
    line-height: 1.7;
  }

  /* ===============================
     Elementos reutilizáveis
  ================================== */
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.4rem 1.2rem;
    border-radius: 999px;
    border: 1px solid var(--border);
    background: rgba(255, 30, 86, 0.12);
    text-transform: uppercase;
    font-size: 0.85rem;
    letter-spacing: 0.15em;
    color: var(--muted);
  }
  .muted {
    color: var(--muted);
  }
  .grid {
    display: grid;
    gap: 1.2rem;
  }
  .grid-4 { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); }
  .grid-3 { grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); }
  .grid-2 { grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); }
  .card {
    position: relative;
    background: var(--card);
    border-radius: 24px;
    padding: 1.35rem;
    border: 1px solid rgba(255, 30, 86, 0.24);
    overflow: hidden;
  }
  .card::after {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at top right, rgba(255, 30, 86, 0.12), transparent 55%);
    pointer-events: none;
  }
  .card h3 {
    font-size: 0.95rem;
    text-transform: uppercase;
    letter-spacing: 0.25em;
    color: var(--muted);
    margin-bottom: 0.4rem;
  }
  .card strong {
    font-size: clamp(1.6rem, 3vw, 2.4rem);
    color: var(--accent);
    display: block;
    margin-bottom: 0.35rem;
  }
  .chip-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
  }
  .chip {
    padding: 0.45rem 1rem;
    border-radius: 999px;
    border: 1px solid var(--border);
    background: rgba(255, 30, 86, 0.1);
    font-size: 0.92rem;
  }
  .list {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .list li {
    padding: 0.85rem 0;
    border-bottom: 1px solid rgba(255, 30, 86, 0.15);
    display: flex;
    gap: 0.6rem;
    align-items: flex-start;
    color: var(--muted);
  }
  .list li span {
    color: var(--accent);
    font-weight: 600;
  }
  .timeline {
    border-left: 2px solid rgba(255, 30, 86, 0.7);
    padding-left: 1.2rem;
    list-style: none;
    margin: 0;
  }
  .timeline li {
    margin-bottom: 1.5rem;
    position: relative;
  }
  .timeline li::before {
    content: "";
    position: absolute;
    left: -1.4rem;
    top: 0.35rem;
    width: 0.8rem;
    height: 0.8rem;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 0 6px rgba(255, 30, 86, 0.15);
  }
  .timeline span {
    display: block;
    font-weight: 700;
    color: var(--accent);
    margin-bottom: 0.25rem;
  }
  blockquote {
    margin: 0;
    padding: 1.7rem;
    border-radius: 24px;
    border: 1px solid rgba(255, 30, 86, 0.3);
    background: linear-gradient(120deg, rgba(255, 30, 86, 0.12), rgba(0,0,0,0.6));
    font-style: italic;
    line-height: 1.8;
    color: var(--muted);
  }
  blockquote span {
    display: block;
    margin-top: 0.8rem;
    letter-spacing: 0.2em;
    font-size: 0.85rem;
    text-transform: uppercase;
    color: var(--accent);
  }
  footer {
    margin-top: 3rem;
    text-align: center;
    color: var(--muted);
    font-size: 0.95rem;
  }
  footer span {
    color: var(--accent);
    font-weight: 700;
  }
</style>
</head>

<body>
<main>

  <!-- Hero -->
  <section>
    <div class="badge">⚙️ Primeiro computador eletrônico</div>
    <h1>ENIAC</h1>
    <p class="muted" style="max-width: 780px; margin-top: 0.8rem;">
      O Electronic Numerical Integrator and Computer utilizou 17.468 válvulas de vácuo, 5 milhões de soldas e equipes visionárias
      para acelerar cálculos militares, científicos e matemáticos, inaugurando a era digital em um cenário dominado por preto e vermelho vibrante.
    </p>
    <div class="chip-row" style="margin-top: 1.5rem;">
      <span class="chip">5.000 operações por segundo</span>
      <span class="chip">20 acumuladores decimais</span>
      <span class="chip">150 kW de energia</span>
      <span class="chip">Projetado por Eckert & Mauchly</span>
    </div>
  </section>

  <!-- Métricas -->
  <section>
    <h2>Métricas icônicas</h2>
    <div class="grid grid-4">
      <article class="card"><h3>Dimensão</h3><strong>30 m</strong><p>Estrutura em U ocupando uma sala inteira.</p></article>
      <article class="card"><h3>Peso</h3><strong>27 t</strong><p>Mais pesado que um caminhão articulado.</p></article>
      <article class="card"><h3>Componentes</h3><strong>17.468</strong><p>Válvulas trabalhando em sincronia.</p></article>
      <article class="card"><h3>Consumo</h3><strong>150 kW</strong><p>Energia de uma pequena vila.</p></article>
      <article class="card"><h3>Funções</h3><strong>6</strong><p>Soma, subtração, multiplicação, divisão, raiz e lógica.</p></article>
      <article class="card"><h3>Velocidade</h3><strong>10³ x</strong><p>Mais rápido que cálculos manuais.</p></article>
      <article class="card"><h3>Operadores</h3><strong>80</strong><p>Profissionais para programar e manter.</p></article>
      <article class="card"><h3>Vida útil</h3><strong>1945–1955</strong><p>Uma década impulsionando a ciência.</p></article>
    </div>
  </section>

  <!-- História -->
  <section class="grid grid-2">
    <article>
      <h2>Por que revolucionou</h2>
      <ul class="list">
        <li><span>⚡</span>Processamento totalmente eletrônico, deixando relés no passado.</li>
        <li><span>🔁</span>Fluxo paralelo de dados, acelerando tarefas complexas.</li>
        <li><span>🧠</span>Programação modular com cabos e painéis reconfiguráveis.</li>
        <li><span>🌐</span>Aplicações militares, científicas, meteorológicas e nucleares.</li>
        <li><span>🔭</span>A base para arquiteturas de programas armazenados.</li>
      </ul>
    </article>
    <article>
      <h2>Experiência de programação</h2>
      <ul class="list">
        <li><span>1</span>Planejamento detalhado em fluxogramas físicos.</li>
        <li><span>2</span>Cabos e chaves definindo rotas de pulsos.</li>
        <li><span>3</span>Tabelas plugáveis com constantes e funções.</li>
        <li><span>4</span>Testes intensos antes da execução real.</li>
        <li><span>5</span>Monitoramento contínuo e substituição de válvulas.</li>
      </ul>
    </article>
  </section>

  <!-- Módulos -->
  <section>
    <h2>Módulos principais</h2>
    <div class="grid grid-3">
      <article class="card"><h3>Acumuladores</h3><p>20 registradores decimais de 10 dígitos realizando somas e subtrações a 5.000 ops/s.</p></article>
      <article class="card"><h3>Unidade de funções</h3><p>Executava multiplicações, divisões e raízes quadradas iterativas.</p></article>
      <article class="card"><h3>Controle mestre</h3><p>Sincronizava pulsos e sequenciava instruções programadas.</p></article>
      <article class="card"><h3>Tabelas plugáveis</h3><p>Cartões com constantes reutilizáveis conectados por cabos.</p></article>
      <article class="card"><h3>I/O por cartões</h3><p>Entrada e saída usando equipamentos IBM padrão.</p></article>
      <article class="card"><h3>Relés de temporização</h3><p>Garantiam integridade dos sinais ao longo de cabos extensos.</p></article>
    </div>
  </section>

  <!-- Infraestrutura & Equipe -->
  <section class="grid grid-2">
    <article>
      <h2>Infraestrutura tática</h2>
      <div class="card"><h3>Layout</h3><p>Corredores em U com piso elevado para refrigeração e roteamento.</p></div>
      <div class="card" style="margin-top: 1rem;"><h3>Ambiente</h3><p>Temperatura controlada e monitoramento 24/7 evitavam sobrecargas.</p></div>
      <div class="card" style="margin-top: 1rem;"><h3>Resiliência</h3><p>Falhas isoladas de válvulas não derrubavam a rotina completa.</p></div>
    </article>
    <article>
      <h2>Equipe pioneira</h2>
      <div class="chip-row">
        <span class="chip">👨‍🔧 J. Presper Eckert</span>
        <span class="chip">👨‍🏫 John W. Mauchly</span>
        <span class="chip">👩‍💻 Jean Bartik</span>
        <span class="chip">👩‍💻 Betty Holberton</span>
        <span class="chip">👩‍💻 Kathleen Antonelli</span>
        <span class="chip">👩‍💻 Marlyn Meltzer</span>
        <span class="chip">👩‍💻 Ruth Teitelbaum</span>
      </div>
    </article>
  </section>

  <!-- Linha do tempo -->
  <section>
    <h2>Timeline ENIAC</h2>
    <ul class="timeline">
      <li><span>1942</span>Proposta ao Exército dos EUA para cálculos balísticos.</li>
      <li><span>1943</span>Construção inicia na Moore School sob sigilo.</li>
      <li><span>1945</span>Testes confirmam desempenho sem precedentes.</li>
      <li><span>1946</span>Demonstração pública resolve equações diferenciais em segundos.</li>
      <li><span>1948</span>Atualização para suportar programação com códigos armazenados.</li>
      <li><span>1950</span>Aplicado a pesquisas meteorológicas, nucleares e espaciais.</li>
      <li><span>1955</span>Desativado e preservado em museus e universidades.</li>
    </ul>
  </section>

  <!-- Impacto -->
  <section>
    <h2>Impacto duradouro</h2>
    <div class="grid grid-3">
      <article class="card"><h3>Arquitetura</h3><p>Fundamentou o EDVAC e consolidou a ideia de programas armazenados.</p></article>
      <article class="card"><h3>Ciência</h3><p>Pioneiro em simulações de clima, armamentos e dinâmica de fluidos.</p></article>
      <article class="card"><h3>Indústria</h3><p>Inspirou máquinas comerciais como UNIVAC e IBM 701.</p></article>
    </div>
  </section>

  <!-- Citação -->
  <section>
    <blockquote>
      “O ENIAC eletrificou a matemática em escala inédita. Cada processador moderno ainda pulsa com ecos dessa ousadia em preto e vermelho.”
      <span>Marcos Vínicius</span>
    </blockquote>
  </section>

  <!-- Rodapé -->
  <footer>
    Feito com orgulho por <span>Marcos Vínicius</span> • Celebrando o ENIAC em preto e vermelho vibrante
  </footer>

</main>
</body>
</html>
