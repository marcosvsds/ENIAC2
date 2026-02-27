<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>ENIAC • Marcos Vínicius</title>
<style>
  :root {
    color-scheme: dark;
    --black: #040404;
    --black-soft: #0c0c0c;
    --card: #111111;
    --border: rgba(255, 30, 86, 0.35);
    --red: #ff1e56;
    --red-dark: #b10032;
    --red-glow: rgba(255, 30, 86, 0.15);
    --text: #f5f5f5;
    --muted: #c7c7c7;
  }
  * {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: "Inter", "Segoe UI", system-ui, -apple-system, sans-serif;
    background: radial-gradient(circle at top, #1a1a1a 0%, var(--black) 45%, #010101 100%);
    color: var(--text);
    min-height: 100vh;
    padding: clamp(1rem, 3vw, 2.5rem);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  main {
    width: min(1200px, 100%);
    background: linear-gradient(145deg, rgba(0,0,0,0.95), rgba(6,6,6,0.8));
    border-radius: 32px;
    padding: clamp(1.5rem, 4vw, 3.5rem);
    border: 1px solid rgba(255, 30, 86, 0.25);
    box-shadow: 0 40px 120px rgba(0, 0, 0, 0.8), 0 0 80px rgba(255, 30, 86, 0.15);
  }
  section + section {
    margin-top: 2.75rem;
  }
  h1, h2, h3 {
    margin: 0;
    letter-spacing: 0.04em;
  }
  h1 {
    font-size: clamp(2.6rem, 5vw, 3.8rem);
    text-transform: uppercase;
  }
  h2 {
    font-size: clamp(1.6rem, 3vw, 2.3rem);
    color: var(--red);
    margin-bottom: 1rem;
  }
  p {
    margin: 0;
    line-height: 1.7;
    color: var(--text);
  }
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
  .hero {
    display: grid;
    gap: 1.5rem;
    text-align: center;
  }
  .hero p {
    color: var(--muted);
    max-width: 760px;
    margin-inline: auto;
  }
  .hero-highlights {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    justify-content: center;
  }
  .hero-highlights span {
    background: rgba(255, 30, 86, 0.14);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 0.7rem 1.2rem;
    font-weight: 600;
    color: var(--text);
  }
  .grid {
    display: grid;
    gap: 1.2rem;
  }
  .grid-4 {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  .grid-3 {
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  }
  .grid-2 {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }
  .card {
    background: var(--card);
    border-radius: 22px;
    padding: 1.3rem;
    border: 1px solid rgba(255, 30, 86, 0.2);
    position: relative;
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
    font-size: 1rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.2em;
    margin-bottom: 0.5rem;
  }
  .card strong {
    font-size: clamp(1.5rem, 3vw, 2.2rem);
    color: var(--red);
    display: block;
    margin-bottom: 0.3rem;
  }
  .split {
    display: grid;
    gap: 1.5rem;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }
  .list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  .list li {
    padding: 0.85rem 0;
    border-bottom: 1px solid rgba(255, 30, 86, 0.15);
    display: flex;
    gap: 0.6rem;
    align-items: start;
    color: var(--muted);
  }
  .list li span {
    color: var(--red);
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
    background: var(--red);
    box-shadow: 0 0 0 6px rgba(255, 30, 86, 0.15);
  }
  .timeline span {
    display: block;
    font-weight: 700;
    color: var(--red);
    margin-bottom: 0.2rem;
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
    color: var(--text);
  }
  blockquote {
    margin: 0;
    padding: 1.7rem;
    border-radius: 24px;
    border: 1px solid rgba(255, 30, 86, 0.35);
    background: linear-gradient(120deg, rgba(255, 30, 86, 0.12), rgba(0,0,0,0.7));
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
    color: var(--red);
  }
  .footer {
    margin-top: 3rem;
    text-align: center;
    color: var(--muted);
    font-size: 0.95rem;
  }
  .footer span {
    color: var(--red);
    font-weight: 700;
  }
</style>
</head>
<body>
<main>
  <section class="hero">
    <span class="badge">⚙️ Primeiro computador eletrônico de propósito geral</span>
    <h1>ENIAC</h1>
    <p>
      O Electronic Numerical Integrator and Computer uniu 17.468 válvulas de vácuo, 5 milhões de soldas e equipes visionárias para executar
      cálculos que redefiniram a computação. A máquina ocupava 170 m², consumia 150 kW e abriu caminho para a era digital.
    </p>
    <div class="hero-highlights">
      <span>5.000 operações por segundo</span>
      <span>20 acumuladores decimais</span>
      <span>150 kW de potência contínua</span>
      <span>Projetado por Eckert & Mauchly</span>
    </div>
  </section>

  <section>
    <h2>Métricas que impressionam</h2>
    <div class="grid grid-4">
      <div class="card"><h3>Dimensão</h3><strong>30 m</strong><p>Estrutura em U ocupando uma sala inteira.</p></div>
      <div class="card"><h3>Peso</h3><strong>27 t</strong><p>Mais pesado que um caminhão articulado.</p></div>
      <div class="card"><h3>Componentes</h3><strong>17.468</strong><p>Válvulas de vácuo operando em sincronia.</p></div>
      <div class="card"><h3>Energia</h3><strong>150 kW</strong><p>Consumo de uma pequena vila acesa.</p></div>
      <div class="card"><h3>Funções</h3><strong>6</strong><p>Soma, subtração, multiplicação, divisão, raiz e lógica.</p></div>
      <div class="card"><h3>Velocidade</h3><strong>10³</strong><p>Vezes mais rápido que cálculos manuais da época.</p></div>
      <div class="card"><h3>Operadores</h3><strong>80</strong><p>Pessoas treinadas para programar e manter.</p></div>
      <div class="card"><h3>Vida útil</h3><strong>1945–1955</strong><p>Uma década impulsionando ciência e defesa.</p></div>
    </div>
  </section>

  <section class="split">
    <div>
      <h2>Por que foi revolucionário</h2>
      <ul class="list">
        <li><span>⚡</span>Processamento totalmente eletrônico, abolindo partes mecânicas lentas.</li>
        <li><span>🔁</span>Fluxo de dados paralelo, permitindo múltiplas operações simultâneas.</li>
        <li><span>🧠</span>Programação modular com cabos e painéis, gerando lógica reconfigurável.</li>
        <li><span>🌐</span>Suporte a projetos militares, meteorológicos e nucleares.</li>
        <li><span>🛠️</span>Documentação e métodos que originaram o conceito de programas armazenados.</li>
      </ul>
    </div>
    <div>
      <h2>Experiência de programação</h2>
      <ul class="list">
        <li><span>1</span>Equipe elaborava fluxogramas e sequências matemáticas.</li>
        <li><span>2</span>Cabos e chaves eram conectados para definir rotas dos pulsos.</li>
        <li><span>3</span>Tabelas de função recebiam constantes através de cartões.</li>
        <li><span>4</span>Testes exaustivos garantiam consistência antes de executar a tarefa real.</li>
        <li><span>5</span>Monitoramento constante substituía válvulas desgastadas sem desligar todo o sistema.</li>
      </ul>
    </div>
  </section>

  <section>
    <h2>Linha do tempo</h2>
    <ul class="timeline">
      <li><span>1942</span>Mauchly e Eckert apresentam a ideia ao Exército dos EUA para cálculos balísticos.</li>
      <li><span>1943</span>Construção começa na Moore School sob sigilo militar.</li>
      <li><span>1945</span>Primeiros testes confirmam desempenho extraordinário.</li>
      <li><span>1946</span>Demonstração pública: o ENIAC resolve equações diferenciais em segundos.</li>
      <li><span>1948</span>Atualização para um sistema de programações por códigos armazenados.</li>
      <li><span>1950</span>Aplicado em pesquisas meteorológicas, nucleares e espaciais.</li>
      <li><span>1955</span>Desativado e distribuído entre museus e instituições de pesquisa.</li>
    </ul>
  </section>

  <section>
    <h2>Módulos e funções</h2>
    <div class="grid grid-3">
      <div class="card"><h3>Acumuladores</h3><p>Vinte registradores decimais de 10 dígitos realizando até 5.000 somas por segundo.</p></div>
      <div class="card"><h3>Unidade de funções</h3><p>Módulo especializado que executava multiplicações, divisões e raízes iterativas.</p></div>
      <div class="card"><h3>Controle mestre</h3><p>Gerava pulsos sincronizados para orquestrar a sequência programada.</p></div>
      <div class="card"><h3>Tabelas plugáveis</h3><p>Cartões substituíveis com constantes e funções pré-calculadas.</p></div>
      <div class="card"><h3>Conversão de cartões</h3><p>Entrada e saída com perfuradoras IBM, integrando-se a fluxos administrativos.</p></div>
      <div class="card"><h3>Relés de temporização</h3><p>Garantiam que sinais cruzassem longos cabos sem perder coerência.</p></div>
    </div>
  </section>

  <section class="split">
    <div>
      <h2>Blueprint operacional</h2>
      <div class="card">
        <h3>Infraestrutura</h3>
        <p>Filas de painéis em forma de U com pisos elevados para ventilação e cabos de energia dedicados.</p>
      </div>
      <div class="card">
        <h3>Ambiente</h3>
        <p>Temperatura controlada e monitoramento 24/7 impediam sobreaquecimentos e quedas de tensão.</p>
      </div>
      <div class="card">
        <h3>Redundância</h3>
        <p>Válvulas eram agrupadas de forma que falhas isoladas não derrubassem toda a rotina.</p>
      </div>
    </div>
    <div>
      <h2>Equipe pioneira</h2>
      <div class="chip-row">
        <span class="chip">👨‍🔧 J. Presper Eckert • Engenheiro-chefe</span>
        <span class="chip">👨‍🏫 John W. Mauchly • Concepção lógica</span>
        <span class="chip">👩‍💻 Jean Bartik • Programadora líder</span>
        <span class="chip">👩‍💻 Betty Holberton • Interface e testes</span>
        <span class="chip">👩‍💻 Kathleen Antonelli • Sequências lógicas</span>
        <span class="chip">👩‍💻 Marlyn Meltzer • Conversão de dados</span>
        <span class="chip">👩‍💻 Ruth Teitelbaum • Debug físico</span>
      </div>
    </div>
  </section>

  <section>
    <h2>Impacto duradouro</h2>
    <div class="grid grid-3">
      <div class="card"><h3>Arquitetura</h3><p>Inspirou o EDVAC e consolidou a ideia de armazenar instruções em memória.</p></div>
      <div class="card"><h3>Ciência</h3><p>Pioneiro em simulações meteorológicas, nucleares e de dinâmica de fluidos.</p></div>
      <div class="card"><h3>Indústria</h3><p>Abriu espaço para computadores comerciais como o UNIVAC e o IBM 701.</p></div>
    </div>
  </section>

  <section>
    <blockquote>
      “O ENIAC provou que a matemática poderia ser eletrificada em grande escala. Cada processador moderno ainda carrega faíscas
      dessa ousadia em preto e vermelho.”
      <span>Marcos Vínicius</span>
    </blockquote>
  </section>

  <div class="footer">
    Feito com dedicação por <span>Marcos Vínicius</span> • Celebrando o legado do primeiro computador eletrônico com um toque moderno preto e vermelho
  </div>
</main>
</body>
</html>
