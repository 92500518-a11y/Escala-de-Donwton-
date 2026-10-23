<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Escala de Downton</title>
  <style>
    :root {
      --bg: #fff7f9;
      --bg-2: #ffeaf1;
      --panel: #ffffff;
      --panel-soft: #fff0f4;
      --rose-1: #ff8fab;
      --rose-2: #f65d8c;
      --rose-3: #d64074;
      --rose-4: #f9c7d7;
      --text: #3b1d2f;
      --muted: #6d4b5f;
      --line: rgba(214, 64, 116, 0.12);
      --success: #e76b95;
      --warning: #ffb46b;
      --danger: #d94c7d;
      --shadow: 0 18px 50px rgba(214, 64, 116, 0.12);
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(180deg, var(--bg) 0%, #fff3f7 100%);
      color: var(--text);
      line-height: 1.7;
    }

    a {
      text-decoration: none;
      color: var(--rose-3);
    }

    .container {
      width: min(1100px, calc(100% - 32px));
      margin: 0 auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 50;
      background: rgba(255, 247, 249, 0.8);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--line);
    }

    nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 18px 0;
    }

    .brand {
      font-weight: 800;
      letter-spacing: 0.1em;
      color: var(--rose-3);
      font-size: 0.94rem;
    }

    .nav-links {
      display: flex;
      gap: 22px;
      font-size: 0.92rem;
      color: var(--muted);
    }

    .nav-links a:hover {
      color: var(--rose-3);
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 150px;
      padding: 12px 22px;
      border-radius: 999px;
      background: linear-gradient(135deg, var(--rose-2), var(--rose-3));
      color: white;
      font-weight: 700;
      box-shadow: var(--shadow);
      transition: transform 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn.secondary {
      background: transparent;
      border: 1px solid var(--line);
      color: var(--text);
      box-shadow: none;
    }

    .hero {
      padding: 60px 0 40px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.25fr 0.95fr;
      gap: 30px;
      align-items: center;
    }

    .eyebrow {
      display: inline-block;
      padding: 8px 14px;
      border-radius: 999px;
      background: rgba(246, 93, 140, 0.08);
      color: var(--rose-3);
      border: 1px solid rgba(246, 93, 140, 0.15);
      font-size: 0.72rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      font-weight: 700;
      margin-bottom: 18px;
    }

    h1 {
      margin: 0;
      font-size: clamp(2.5rem, 5vw, 4.4rem);
      line-height: 1.06;
      letter-spacing: -0.05em;
      color: var(--text);
    }

    .hero p {
      color: var(--muted);
      font-size: 1.08rem;
      max-width: 620px;
      margin-top: 18px;
    }

    .hero-actions {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      margin-top: 28px;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
      margin-top: 28px;
    }

    .stat {
      background: rgba(255,255,255,0.5);
      border: 1px solid var(--line);
      border-radius: 18px;
      padding: 18px 16px;
      box-shadow: var(--shadow);
    }

    .stat strong {
      display: block;
      font-size: 1.5rem;
      margin-bottom: 4px;
      color: var(--text);
    }

    .stat span {
      color: var(--muted);
      font-size: 0.82rem;
    }

    .hero-card {
      background: linear-gradient(180deg, #fff7fa 0%, #fff1f6 100%);
      border: 1px solid var(--line);
      border-radius: 26px;
      overflow: hidden;
      box-shadow: var(--shadow);
    }

    .card-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 18px 20px;
      border-bottom: 1px solid var(--line);
      background: rgba(255,255,255,0.4);
    }

    .label-mini {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .badge {
      background: rgba(246, 93, 140, 0.12);
      color: var(--rose-3);
      border: 1px solid rgba(246, 93, 140, 0.18);
      padding: 7px 10px;
      border-radius: 999px;
      font-size: 0.72rem;
      font-weight: 700;
    }

    .card-body {
      padding: 22px 20px 20px;
    }

    .score-box {
      background: rgba(255, 143, 171, 0.08);
      border: 1px solid rgba(246, 93, 140, 0.12);
      border-radius: 20px;
      padding: 18px 16px;
      margin-bottom: 18px;
    }

    .mini-label {
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      font-size: 0.72rem;
      margin-bottom: 8px;
    }

    .score {
      font-size: clamp(2.2rem, 4vw, 3.2rem);
      font-weight: 800;
      letter-spacing: -0.04em;
      color: var(--text);
    }

    .level-box {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 10px 14px;
      border-radius: 12px;
      font-weight: 700;
      border: 1px solid rgba(246, 93, 140, 0.2);
      background: rgba(255, 143, 171, 0.08);
      color: var(--rose-3);
    }

    .level-box::before {
      content: "";
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: currentColor;
      box-shadow: 0 0 12px currentColor;
    }

    section {
      padding: 28px 0 18px;
    }

    .section-header {
      margin-bottom: 18px;
    }

    .section-header h2 {
      margin: 0 0 8px;
      font-size: clamp(1.8rem, 3vw, 2.7rem);
      letter-spacing: -0.04em;
    }

    .section-header p {
      color: var(--muted);
      margin: 0;
      max-width: 760px;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 22px;
      margin-top: 20px;
    }

    .card {
      background: rgba(255,255,255,0.55);
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 22px 20px;
      box-shadow: var(--shadow);
    }

    .card h3 {
      margin: 0 0 12px;
      font-size: 1.2rem;
    }

    .card p, .card li {
      color: var(--muted);
    }

    .card ul {
      margin: 0;
      padding-left: 18px;
    }

    .info-panel {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 24px;
      margin-top: 18px;
    }

    .scientific {
      background: rgba(255,255,255,0.55);
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 24px;
      box-shadow: var(--shadow);
    }

    .scientific h3 {
      margin-top: 0;
      font-size: 1.5rem;
    }

    .chip-list {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 20px;
    }

    .chip {
      background: rgba(246, 93, 140, 0.08);
      border: 1px solid rgba(246, 93, 140, 0.15);
      color: var(--rose-3);
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 0.78rem;
      font-weight: 700;
    }

    .quote {
      margin-top: 22px;
      padding: 18px 20px;
      border-left: 4px solid var(--rose-2);
      background: rgba(255, 143, 171, 0.08);
      border-radius: 12px;
      font-style: italic;
      color: var(--text);
    }

    .levels {
      background: rgba(255,255,255,0.55);
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 22px 20px;
      box-shadow: var(--shadow);
    }

    .levels-table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 16px;
    }

    .levels-table th,
    .levels-table td {
      text-align: left;
      padding: 12px 8px;
      border-bottom: 1px solid var(--line);
    }

    .levels-table th {
      color: var(--text);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      font-size: 0.72rem;
    }

    .levels-table td {
      color: var(--muted);
    }

    .about {
      display: grid;
      grid-template-columns: 0.95fr 1.05fr;
      gap: 24px;
      margin-top: 24px;
    }

    .about-card {
      background: rgba(255,255,255,0.55);
      border: 1px solid var(--line);
      border-radius: 24px;
      padding: 24px 20px;
      box-shadow: var(--shadow);
    }

    .about-card h3 {
      margin-top: 0;
      font-size: 1.4rem;
    }

    .author-box {
      background: linear-gradient(135deg, rgba(246,93,140,0.12), rgba(255,233,239,0.9));
      border-radius: 18px;
      border: 1px solid rgba(246,93,140,0.12);
      padding: 18px;
      margin-top: 16px;
    }

    .author-box strong {
      display: block;
      font-size: 1.1rem;
      margin-bottom: 8px;
    }

    .personalized {
      margin-top: 22px;
      padding: 18px 20px;
      border-radius: 18px;
      background: rgba(246, 93, 140, 0.08);
      border: 1px solid rgba(246,93,140,0.12);
      transition: all 0.25s ease;
    }

    .personalized h3 {
      margin: 0 0 8px;
      font-size: 1.2rem;
    }

    .personalized p {
      margin: 0;
      color: var(--muted);
      line-height: 1.7;
    }

    footer {
      margin-top: 48px;
      border-top: 1px solid var(--line);
      padding: 34px 0 60px;
      text-align: center;
      color: var(--muted);
    }

    @media (max-width: 900px) {
      .hero-grid,
      .info-panel,
      .about {
        grid-template-columns: 1fr;
      }

      .grid-3 {
        grid-template-columns: 1fr;
      }

      .nav-links {
        display: none;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <nav>
        <div class="brand">ESCALA DE DOWNTON</div>
        <div class="nav-links">
          <a href="#que-es">Qué es</a>
          <a href="#cientifico">Científico</a>
          <a href="#interpretacion">Interpretación</a>
          <a href="#quien-lo-creo">¿Quién lo creó?</a>
        </div>
        <a class="btn" href="#quien-lo-creo">Más información</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow">Herramienta de evaluación</div>
          <h1>Escala de Downton</h1>
          <p>
            La escala de Downton es un instrumento orientado a la observación, valoración y
            análisis estructurado de un fenómeno concreto, con finalidad de facilitar la
            interpretación de resultados y apoyar la toma de decisiones con base científica.
          </p>

          <div class="hero-actions">
            <a class="btn" href="#cientifico">Ver información</a>
            <a class="btn secondary" href="#interpretacion">Interpretación</a>
          </div>

          <div class="stats">
            <div class="stat">
              <strong>0–30</strong>
              <span>Rango posible</span>
            </div>
            <div class="stat">
              <strong>5 niveles</strong>
              <span>Clasificación</span>
            </div>
            <div class="stat">
              <strong>Psicometría</strong>
              <span>Base metodológica</span>
            </div>
          </div>
        </div>

        <div class="hero-card">
          <div class="card-top">
            <span class="label-mini">Evaluación rápida</span>
            <span class="badge">Actual</span>
          </div>

          <div class="card-body">
            <div class="score-box">
              <div class="mini-label">Puntuación</div>
              <div class="score" id="scoreValue">16</div>
            </div>

            <div class="mini-label">Nivel</div>
            <div class="level-box" id="levelBox">Severidad alta</div>
          </div>
        </div>
      </div>
    </section>

    <section id="que-es">
      <div class="container">
        <div class="section-header">
          <h2>¿Qué es la Escala de Downton?</h2>
          <p>
            Es una herramienta de medición diseñada para valorar la intensidad o gravedad de un
            determinado constructo, permitiendo comparar resultados y seguir su evolución con mayor precisión.
          </p>
        </div>

        <div class="grid-3">
          <article class="card">
            <h3>Objetivo</h3>
            <p>
              Cuantificar signos, síntomas o situaciones para transformar observaciones cualitativas
              en indicadores más claros y comparables.
            </p>
          </article>

          <article class="card">
            <h3>Aplicación</h3>
            <p>
              Se usa en contextos clínicos, formativos, investigativos y de seguimiento, siempre
              bajo criterios estructurados y con interpretación adecuada.
            </p>
          </article>

          <article class="card">
            <h3>Valor útil</h3>
            <p>
              Ayuda a detectar niveles de riesgo, evolución del caso o necesidad de intervención,
              favoreciendo una evaluación más ordenada y objetiva.
            </p>
          </article>
        </div>
      </div>
    </section>

    <section id="cientifico">
      <div class="container">
        <div class="section-header">
          <h2>Información científica</h2>
          <p>
            Una escala con valor científico debe estar fundamentada en validez, confiabilidad,
            análisis estadístico y criterios metodológicos claros.
          </p>
        </div>

        <div class="info-panel">
          <div class="scientific">
            <h3>Principios metodológicos</h3>
            <p>
              La robustez de una escala depende de su capacidad para medir de forma estable y
              consistente aquello que pretende evaluar. Para ello, se suelen considerar aspectos
              como la validez de contenido, la fiabilidad interna y la consistencia entre evaluaciones.
            </p>

            <div class="chip-list">
              <span class="chip">Validez</span>
              <span class="chip">Confiabilidad</span>
              <span class="chip">Fiabilidad interna</span>
              <span class="chip">Análisis psicométrico</span>
              <span class="chip">Interpretación clínica</span>
            </div>

            <div class="quote">
              “La medición estructurada mejora la precisión diagnóstica y hace más clara la
              interpretación del caso.”
            </div>
          </div>

          <div class="levels">
            <h3>Rangos</h3>
            <table class="levels-table">
              <thead>
                <tr>
                  <th>Puntuación</th>
                  <th>Clasificación</th>
                </tr>
              </thead>
              <tbody>
                <tr><td>0–5</td><td>Muy baja</td></tr>
                <tr><td>6–10</td><td>Baja</td></tr>
                <tr><td>11–15</td><td>Moderada</td></tr>
                <tr><td>16–20</td><td>Alta</td></tr>
                <tr><td>21–30</td><td>Muy alta</td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </section>

    <section id="interpretacion">
      <div class="container">
        <div class="section-header">
          <h2>Interpretación personalizada según la puntuación</h2>
          <p>
            La clave no es solo la puntuación, sino la forma en que se contextualiza. A continuación
            se presenta una guía práctica para entender mejor cada rango.
          </p>
        </div>

        <div class="personalized" id="personalizedBox">
          <h3 id="personalizedTitle">Se requiere atención</h3>
          <p id="personalizedText">
            Tu nivel actual se encuentra en un rango elevado. Es recomendable observar con atención
            el contexto, revisar patrones de esfuerzo o molestias y considerar un acompañamiento
            profesional si la situación persiste.
          </p>
        </div>

        <div class="grid-3">
          <article class="card">
            <h3>0–5</h3>
            <p>Muy bajo. Se observa una ausencia clara de indicadores relevantes. Mantener vigilancia y seguimiento preventivo.</p>
          </article>

          <article class="card">
            <h3>6–10</h3>
            <p>Bajo. Se presentan leves señales. Puede ser útil reforzar hábitos, descanso y observación durante un tiempo.</p>
          </article>

          <article class="card">
            <h3>11–15</h3>
            <p>Moderado. Hay presencia de indicadores significativos. Se recomienda un análisis más detenido y apoyo sostenido.</p>
          </article>
        </div>

        <div class="grid-3" style="margin-top: 22px;">
          <article class="card">
            <h3>16–20</h3>
            <p>Alto. El nivel requiere atención activa y una revisión contextual más profunda para valorar la intensidad real.</p>
          </article>

          <article class="card">
            <h3>21–30</h3>
            <p>Muy alto. Se recomienda valoración profesional con urgencia, dado que el impacto puede ser significativo.</p>
          </article>

          <article class="card">
            <h3>Recomendación general</h3>
            <p>La interpretación debe combinar la puntuación con la historia personal, la situación y la dimensión evaluada.</p>
          </article>
        </div>
      </div>
    </section>

    <section id="quien-lo-creo">
      <div class="container">
        <div class="section-header">
          <h2>¿Quién lo creó?</h2>
          <p>
            En la práctica científica, este tipo de instrumentos suelen ser desarrollados por equipos
            de especialistas en investigación, psicometría y atención profesional, con validación empírica.
          </p>
        </div>

        <div class="about">
          <div class="about-card">
            <h3>Autoría y desarrollo</h3>
            <p>
              La escala no suele responder a una sola persona aislada, sino a un conjunto de profesionales
              que diseña, valida y ajusta el instrumento con base en evidencia, revisión bibliográfica y prácticas clínicas.
            </p>

            <div class="author-box">
              <strong>Referencia general</strong>
              <p>
                Un sitio académico o profesional normalmente presenta al autor principal, la institución
                que lo desarrolló y las publicaciones que respaldan su validación.
              </p>
            </div>
          </div>

          <div class="about-card">
            <h3>Cómo se presenta en una página institucional</h3>
            <ul>
              <li>Nombre del instrumento</li>
              <li>Autor o equipo investigador</li>
              <li>Institución o centro académico</li>
              <li>Año de creación o validación</li>
              <li>Referencias científicas</li>
              <li>Contexto de aplicación</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    © 2026 Escala de Downton · Página informativa con enfoque científico
  </footer>

  <script>
    const scoreValue = document.getElementById("scoreValue");
    const levelBox = document.getElementById("levelBox");
    const personalizedTitle = document.getElementById("personalizedTitle");
    const personalizedText = document.getElementById("personalizedText");

    function getInterpretation(value) {
      if (value <= 5) {
        return {
          label: "Severidad muy baja",
          title: "Estado muy estable",
          text: "Tu puntuación es baja y sugiere que no se observan señales relevantes de intensidad elevada. Mantén hábitos saludables y continúa con seguimiento preventivo si lo consideras necesario.",
          color: "#d98aa3"
        };
      } else if (value <= 10) {
        return {
          label: "Severidad baja",
          title: "Se recomienda seguimiento ligero",
          text: "Se observa una presencia leve de indicadores. Puedes reforzar hábitos de descanso, autocuidado y revisión de tu rutina para sostener un equilibrio saludable.",
          color: "#e7779f"
        };
      } else if (value <= 15) {
        return {
          label: "Severidad moderada",
          title: "Se requiere observación",
          text: "Tu nivel indica que hay una presencia clara de indicadores. Es recomendable analizar el contexto, identificar patrones y considerar un acompañamiento más continuo.",
          color: "#d95f8f"
        };
      } else if (value <= 20) {
        return {
          label: "Severidad alta",
          title: "Se requiere atención",
          text: "La puntuación actual refleja un nivel elevado que merece atención más activa. Se recomienda revisar el entorno, reducir factores que lo agravan y valorar apoyo profesional.",
          color: "#c94d7f"
        };
      } else {
        return {
          label: "Severidad muy alta",
          title: "Se requiere apoyo profesional",
          text: "Tu nivel se encuentra en un rango elevado y puede requerir valoración más profunda. Es recomendable buscar apoyo especializado para una evaluación individualizada y segura.",
          color: "#b9466d"
        };
      }
    }

    function updateEvaluation(value) {
      const interpretation = getInterpretation(value);
      scoreValue.textContent = value;
      levelBox.textContent = interpretation.label;
      levelBox.style.color = interpretation.color;
      levelBox.style.borderColor = interpretation.color + "50";
      levelBox.style.background = interpretation.color + "14";

      personalizedTitle.textContent = interpretation.title;
      personalizedText.textContent = interpretation.text;
    }

    updateEvaluation(16);
  </script>
</body>
</html>
