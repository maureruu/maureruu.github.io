<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>SENTINEL — IA &amp; Ciberseguridad</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
:root{
  --bg:#0b0f14;
  --bg-panel:#11161d;
  --line:#22303d;
  --ink:#dbe6ec;
  --ink-dim:#8fa3b0;
  --amber:#ffb454;
  --cyan:#5fd8d0;
  --red:#ff6b5e;
  --mono: 'JetBrains Mono', 'Courier New', monospace;
  --serif: 'Georgia', 'Times New Roman', serif;
  --sans: 'Helvetica Neue', Arial, sans-serif;
}
*{box-sizing:border-box;}
body{
  margin:0; background:var(--bg); color:var(--ink);
  font-family:var(--sans); line-height:1.55;
}
.page{
  max-width:1000px; margin:0 auto; background:var(--bg);
  border-left:1px solid var(--line); border-right:1px solid var(--line);
  position:relative;
}
.section{ padding:90px 70px; border-bottom:1px solid var(--line); position:relative;}
@media (max-width:700px){ .section{padding:60px 28px;} }

.eyebrow{
  font-family:var(--mono); font-size:12px; letter-spacing:.18em; text-transform:uppercase;
  color:var(--amber);
}
.hairline{ height:1px; background:var(--line); width:100%; margin:24px 0;}

/* ---------- COVER ---------- */
.cover{
  min-height:100vh; display:flex; flex-direction:column; justify-content:space-between;
  background:
    radial-gradient(circle at 80% 8%, rgba(95,216,208,0.10), transparent 45%),
    radial-gradient(circle at 10% 90%, rgba(255,180,84,0.08), transparent 40%),
    var(--bg);
  border-bottom:1px solid var(--line);
}
.cover-top{ display:flex; justify-content:space-between; align-items:flex-start; padding:48px 70px 0;}
.cover-top .tag{ font-family:var(--mono); font-size:11px; color:var(--ink-dim); letter-spacing:.12em;}
.brand{
  text-align:center; padding:40px 20px 0;
}
.brand .mark{
  font-family:var(--mono); color:var(--cyan); font-size:13px; letter-spacing:.3em; text-transform:uppercase;
}
.brand h1{
  font-family:var(--serif); font-size:118px; margin:6px 0 0; letter-spacing:-2px; color:var(--ink);
  text-shadow:0 0 40px rgba(95,216,208,0.15);
}
.brand .sub{
  font-family:var(--mono); color:var(--ink-dim); font-size:14px; letter-spacing:.05em; margin-top:6px;
}
.cover-grid{
  display:grid; grid-template-columns:1fr 1fr; gap:1px; background:var(--line);
  margin:60px 0 0; border-top:1px solid var(--line); border-bottom:1px solid var(--line);
}
.cover-grid .cell{ background:var(--bg); padding:30px 70px;}
.cover-grid .cell .num{ font-family:var(--mono); color:var(--red); font-size:12px;}
.cover-grid .cell h3{ margin:8px 0 0; font-size:21px; font-weight:600;}
.cover-bottom{
  display:flex; justify-content:space-between; align-items:center; padding:30px 70px 50px;
  font-family:var(--mono); font-size:12px; color:var(--ink-dim);
}

/* ---------- TOC ---------- */
.toc-list{ margin-top:30px;}
.toc-item{
  display:grid; grid-template-columns:60px 1fr auto; align-items:baseline;
  padding:22px 0; border-bottom:1px solid var(--line); gap:20px;
}
.toc-item .idx{ font-family:var(--mono); color:var(--cyan); font-size:22px;}
.toc-item .ttl{ font-size:20px; font-weight:600;}
.toc-item .desc{ display:block; font-size:13px; color:var(--ink-dim); font-weight:400; margin-top:4px;}
.toc-item .pg{ font-family:var(--mono); color:var(--ink-dim); font-size:13px;}

/* ---------- EDITOR ---------- */
.editor-wrap{ display:grid; grid-template-columns:140px 1fr; gap:40px;}
.editor-mark{ font-family:var(--serif); font-size:90px; color:var(--cyan); line-height:1; opacity:.8;}
.editor h2{ font-family:var(--serif); font-size:38px; margin:0 0 8px;}
.editor p{ font-size:16px; color:var(--ink); max-width:640px;}
.editor .signoff{ margin-top:30px; font-family:var(--mono); font-size:13px; color:var(--ink-dim);}
@media (max-width:700px){ .editor-wrap{grid-template-columns:1fr;} .editor-mark{display:none;} }

/* ---------- ARTICLES ---------- */
.article-head{ display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:20px;}
.article-head h2{
  font-family:var(--serif); font-size:46px; margin:14px 0 0; max-width:680px; line-height:1.08;
}
.article-meta{ font-family:var(--mono); font-size:12px; color:var(--ink-dim); text-align:right;}
.deck{ font-size:18px; color:var(--cyan); margin-top:18px; max-width:680px; font-weight:500;}
.article-body{ margin-top:34px; display:grid; grid-template-columns:2fr 1fr; gap:50px;}
.article-body .col-text p{ font-size:16px; margin-bottom:18px; color:var(--ink);}
.article-body .col-text h4{ font-family:var(--mono); color:var(--amber); font-size:13px; letter-spacing:.08em; text-transform:uppercase; margin:30px 0 10px;}
.sidebar{ border-left:1px solid var(--line); padding-left:30px;}
.sidebar .box{ background:var(--bg-panel); border:1px solid var(--line); padding:20px; margin-bottom:20px;}
.sidebar .box .label{ font-family:var(--mono); font-size:11px; color:var(--red); letter-spacing:.1em; text-transform:uppercase;}
.sidebar .box p, .sidebar .box li{ font-size:14px; color:var(--ink-dim);}
.sidebar ul{ padding-left:18px; margin:8px 0;}
@media (max-width:700px){ .article-body{grid-template-columns:1fr;} .sidebar{border-left:none; padding-left:0; border-top:1px solid var(--line); padding-top:24px;} .article-head h2{font-size:32px;} }

/* ---------- ADS ---------- */
.ads-section{ padding:80px 70px;}
.ads-section .eyebrow{ display:block; margin-bottom:40px;}
.ad-grid{ display:grid; grid-template-columns:1fr 1fr; gap:24px;}
.ad{
  border:1px solid var(--line); padding:36px 30px; background:var(--bg-panel);
  display:flex; flex-direction:column; justify-content:space-between; min-height:220px;
}
.ad.full{ grid-column:1/-1;}
.ad .ad-tag{ font-family:var(--mono); font-size:10px; color:var(--ink-dim); letter-spacing:.1em;}
.ad h3{ font-family:var(--serif); font-size:28px; margin:10px 0;}
.ad p{ font-size:14px; color:var(--ink-dim); max-width:480px;}
.ad .cta{
  align-self:flex-start; margin-top:16px; font-family:var(--mono); font-size:12px;
  color:var(--bg); background:var(--cyan); padding:8px 16px; letter-spacing:.05em;
}
@media (max-width:700px){ .ad-grid{grid-template-columns:1fr;} }

/* ---------- AD BANNER (single, between articles) ---------- */
.ad-banner{
  padding:0; border-bottom:1px solid var(--line);
  background:
    radial-gradient(circle at 90% 0%, rgba(255,180,84,0.10), transparent 50%),
    var(--bg-panel);
}
.ad-banner-inner{ padding:60px 70px; display:grid; grid-template-columns:1fr auto; gap:40px; align-items:center;}
.ad-banner .ad-kicker{
  font-family:var(--mono); font-size:11px; letter-spacing:.15em; color:var(--red); text-transform:uppercase;
}
.ad-banner .ad-kicker::before{ content:"PUBLICIDAD · "; color:var(--ink-dim);}
.ad-banner h3{ font-family:var(--serif); font-size:40px; margin:10px 0 12px; line-height:1.05; color:var(--ink);}
.ad-banner .pitch{ font-size:17px; color:var(--ink); max-width:560px; font-weight:500;}
.ad-banner .punch{ font-size:14px; color:var(--cyan); margin-top:10px; font-family:var(--mono);}
.ad-banner-cta{ text-align:center;}
.ad-banner .cta-btn{
  display:inline-block; font-family:var(--mono); font-size:13px; font-weight:700; letter-spacing:.05em;
  color:var(--bg); background:var(--amber); padding:14px 26px; white-space:nowrap;
}
.ad-banner .fine{ display:block; margin-top:10px; font-size:11px; color:var(--ink-dim); font-family:var(--mono);}
.ad-banner.alt .cta-btn{ background:var(--cyan);}
@media (max-width:700px){
  .ad-banner-inner{ grid-template-columns:1fr; padding:44px 28px; text-align:left;}
  .ad-banner-cta{ text-align:left;}
  .ad-banner h3{ font-size:30px;}
}

/* ---------- TRUE MAGAZINE COVER ---------- */
.mcover{
  min-height:100vh; position:relative; overflow:hidden;
  background:
    radial-gradient(circle at 85% 15%, rgba(95,216,208,0.16), transparent 45%),
    radial-gradient(circle at 15% 85%, rgba(255,107,94,0.10), transparent 45%),
    linear-gradient(180deg, #0c1117 0%, #090c10 100%);
  border-bottom:1px solid var(--line);
  display:flex; flex-direction:column;
}
.mcover-grid{ position:absolute; inset:0; opacity:.35;
  background-image:
    linear-gradient(var(--line) 1px, transparent 1px),
    linear-gradient(90deg, var(--line) 1px, transparent 1px);
  background-size:48px 48px;
  mask-image:linear-gradient(180deg, transparent, rgba(0,0,0,0.9) 30%, rgba(0,0,0,0.9) 70%, transparent);
}
.mcover-top{
  position:relative; z-index:2; display:flex; justify-content:space-between; align-items:center;
  padding:34px 60px 0; font-family:var(--mono); font-size:11px; letter-spacing:.14em; color:var(--ink-dim); text-transform:uppercase;
}
.mcover-masthead{
  position:relative; z-index:2; text-align:center; padding:18px 20px 0;
}
.mcover-masthead .kicker{ font-family:var(--mono); color:var(--cyan); font-size:13px; letter-spacing:.35em; text-transform:uppercase;}
.mcover-masthead h1{
  font-family:var(--serif); font-size:160px; margin:2px 0 0; letter-spacing:-4px; line-height:.92;
  color:var(--ink); text-shadow:0 0 60px rgba(95,216,208,0.18);
}
.mcover-masthead .baseline{ font-family:var(--mono); font-size:14px; color:var(--ink-dim); letter-spacing:.08em; margin-top:4px;}
.mcover-cover-lines{
  position:relative; z-index:2; flex:1; display:grid; grid-template-columns:1.1fr 1fr; gap:0; align-items:center; padding:30px 60px 0;
}
.mcover-headline{
  font-family:var(--serif); font-size:54px; line-height:1.04; color:var(--ink); max-width:520px;
}
.mcover-headline em{ color:var(--amber); font-style:normal; font-family:var(--serif);}
.mcover-sub{ font-size:16px; color:var(--ink-dim); max-width:440px; margin-top:18px;}
.mcover-list{ list-style:none; margin:30px 0 0; padding:0; display:flex; flex-direction:column; gap:14px;}
.mcover-list li{
  font-family:var(--mono); font-size:14px; color:var(--ink); display:flex; gap:14px; align-items:baseline;
  border-top:1px solid var(--line); padding-top:14px;
}
.mcover-list li:first-child{ border-top:none; padding-top:0;}
.mcover-list .tick{ color:var(--red); font-size:12px;}
.mcover-side{ text-align:right; align-self:start; padding-top:6px;}
.mcover-side .pill{
  display:inline-block; font-family:var(--mono); font-size:11px; letter-spacing:.1em; color:var(--bg);
  background:var(--amber); padding:6px 14px; margin-bottom:18px;
}
.mcover-side .quote{
  font-family:var(--serif); font-style:italic; font-size:22px; color:var(--ink); line-height:1.3;
}
.mcover-side .quote-by{ font-family:var(--mono); font-size:12px; color:var(--ink-dim); display:block; margin-top:10px;}
.mcover-bottom{
  position:relative; z-index:2; display:flex; justify-content:space-between; align-items:center;
  padding:40px 60px 50px; font-family:var(--mono); font-size:12px; color:var(--ink-dim);
}
.barcode{ display:flex; align-items:center; gap:6px;}
.barcode .bars{ display:flex; gap:2px; align-items:flex-end; height:30px;}
.barcode .bars span{ width:2px; background:var(--ink-dim); display:block;}
@media (max-width:760px){
  .mcover-masthead h1{ font-size:84px; letter-spacing:-2px;}
  .mcover-cover-lines{ grid-template-columns:1fr; padding:24px 28px 0; gap:30px;}
  .mcover-side{ text-align:left;}
  .mcover-headline{ font-size:36px;}
  .mcover-top, .mcover-bottom{ padding-left:28px; padding-right:28px;}
}

/* ---------- FOOTER ---------- */
.colophon{ padding:60px 70px; font-family:var(--mono); font-size:12px; color:var(--ink-dim); display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;}
</style>
</head>
<body>
<div class="page">

  <!-- ============ PORTADA PRINCIPAL ============ -->
  <div class="mcover">
    <div class="mcover-grid"></div>
    <div class="mcover-top">
      <span>Edición 02 · 2026</span>
      <span>Revista académica digital</span>
    </div>
    <div class="mcover-masthead">
      <div class="kicker">// threat_level: elevated</div>
      <h1>SENTINEL</h1>
      <div class="baseline">inteligencia artificial &amp; ciberseguridad</div>
    </div>
    <div class="mcover-cover-lines">
      <div>
        <div class="mcover-headline">Tu próximo <em>ataque</em><br>ya aprendió a escribir<br>como un humano.</div>
        <p class="mcover-sub">Una mirada a fondo a cómo la inteligencia artificial está reescribiendo, al mismo tiempo, las reglas del ataque y de la defensa digital.</p>
        <ul class="mcover-list">
          <li><span class="tick">▸</span> Prompt Injection: el nuevo phishing de la era de la IA</li>
          <li><span class="tick">▸</span> OWASP Top 10 para Aplicaciones LLM</li>
          <li><span class="tick">▸</span> Cómo los ciberdelincuentes están utilizando IA</li>
          <li><span class="tick">▸</span> IA para la defensa en ciberseguridad</li>
        </ul>
      </div>
      <div class="mcover-side">
        <span class="pill">Edición especial</span>
        <div class="quote">&ldquo;La confianza ciega de un modelo en su propio texto es la nueva puerta trasera.&rdquo;</div>
        <span class="quote-by">— Nota del editor, pág. 04</span>
      </div>
    </div>
    <div class="mcover-bottom">
      <span>Preparado por: Cesar Maure</span>
      <div class="barcode">
        <div class="bars">
          <span style="height:18px;"></span><span style="height:28px;"></span><span style="height:14px;"></span>
          <span style="height:24px;"></span><span style="height:30px;"></span><span style="height:16px;"></span>
          <span style="height:22px;"></span><span style="height:12px;"></span><span style="height:28px;"></span>
          <span style="height:20px;"></span>
        </div>
        <span>SENT-002-26</span>
      </div>
      <span>www.sentinel-mag.dev</span>
    </div>
  </div>

  <!-- ============ PORTADA ============ -->
  <div class="cover section" style="padding:0;">
    <div class="cover-top">
      <span class="tag">RESUMEN DE LA EDICIÓN</span>
      <span class="tag">REVISTA ACADÉMICA DIGITAL</span>
    </div>
    <div class="brand" style="padding-top:20px;">
      <div class="mark">en esta edición</div>
      <h1 style="font-size:54px;">Lo que vas a encontrar</h1>
      <div class="sub">cuatro frentes clave de la batalla entre IA y ciberseguridad</div>
    </div>
    <div class="cover-grid">
      <div class="cell">
        <div class="num">01</div>
        <h3>Prompt Injection: el nuevo phishing</h3>
      </div>
      <div class="cell">
        <div class="num">02</div>
        <h3>OWASP Top 10 para Aplicaciones LLM</h3>
      </div>
      <div class="cell">
        <div class="num">03</div>
        <h3>Cómo los ciberdelincuentes usan la IA</h3>
      </div>
      <div class="cell">
        <div class="num">04</div>
        <h3>IA para la defensa en ciberseguridad</h3>
      </div>
    </div>
    <div class="cover-bottom">
      <span>Preparado por: Cesar Maure</span>
      <span>www.sentinel-mag.dev</span>
    </div>
  </div>

  <!-- ============ TABLA DE CONTENIDO ============ -->
  <div class="section">
    <span class="eyebrow">Índice</span>
    <h2 style="font-family:var(--serif); font-size:42px; margin:14px 0 0;">Tabla de contenido</h2>
    <div class="toc-list">
      <div class="toc-item"><span class="idx">00</span><span class="ttl">Nota del editor<span class="desc">Una mirada al estado de la seguridad en la era de los modelos de lenguaje</span></span><span class="pg">PÁG. 04</span></div>
      <div class="toc-item"><span class="idx">01</span><span class="ttl">OWASP Top 10 para Aplicaciones LLM<span class="desc">El mapa de riesgo que toda aplicación con IA generativa debería conocer</span></span><span class="pg">PÁG. 05</span></div>
      <div class="toc-item"><span class="idx">02</span><span class="ttl">Riesgos críticos en IA generativa<span class="desc">Alucinaciones, fuga de datos y dependencia algorítmica</span></span><span class="pg">PÁG. 07</span></div>
      <div class="toc-item"><span class="idx">03</span><span class="ttl">Prompt Injection: el nuevo phishing<span class="desc">Cuando el ataque se esconde dentro del propio texto</span></span><span class="pg">PÁG. 09</span></div>
      <div class="toc-item"><span class="idx">04</span><span class="ttl">Seguridad y riesgos de herramientas de IA generativa<span class="desc">Lo que las empresas no están midiendo todavía</span></span><span class="pg">PÁG. 11</span></div>
      <div class="toc-item"><span class="idx">05</span><span class="ttl">Cómo los ciberdelincuentes están utilizando IA<span class="desc">Del malware polimórfico a las estafas de voz clonada</span></span><span class="pg">PÁG. 13</span></div>
      <div class="toc-item"><span class="idx">06</span><span class="ttl">IA para la defensa en ciberseguridad<span class="desc">Detección, respuesta y SOC aumentados por modelos</span></span><span class="pg">PÁG. 15</span></div>
    </div>
  </div>

  <!-- ============ NOTA DEL EDITOR ============ -->
  <div class="section editor">
    <span class="eyebrow">Editorial</span>
    <div class="editor-wrap" style="margin-top:14px;">
      <div class="editor-mark">&ldquo;</div>
      <div>
        <h2>Nota del editor</h2>
        <p>
          Cada avance en inteligencia artificial trae consigo una superficie de ataque que todavía no terminamos de
          comprender. En esta edición de SENTINEL decidimos detenernos en un punto incómodo pero necesario: los modelos
          de lenguaje no solo automatizan tareas, también automatizan riesgos.
        </p>
        <p>
          Hemos reunido seis artículos que recorren el problema desde distintos ángulos, desde el marco técnico de
          OWASP para aplicaciones LLM, hasta las tácticas que los atacantes ya están usando para clonar voces,
          escribir correos de phishing perfectos o filtrar datos sensibles a través de un simple mensaje de texto.
          También dedicamos espacio a la otra cara de la moneda: cómo la misma tecnología que crea el riesgo puede
          convertirse en la herramienta más poderosa para detectarlo y contenerlo.
        </p>
        <p>
          No pretendemos dar respuestas definitivas. Pretendemos, sobre todo, instalar la pregunta correcta en el
          lector: ¿estamos diseñando sistemas de IA con la misma disciplina con la que diseñamos sistemas seguros?
          Esperamos que esta edición sea un buen punto de partida.
        </p>
        <div class="signoff">— El equipo editorial de SENTINEL</div>
      </div>
    </div>
  </div>

  <!-- ============ ANUNCIO 1 ============ -->
  <div class="ad-banner">
    <div class="ad-banner-inner">
      <div>
        <div class="ad-kicker">Ciberseguridad</div>
        <h3>Tu red ya fue escaneada hoy.<br>¿Lo sabías?</h3>
        <p class="pitch">NebulaShield detecta movimientos sospechosos en segundos, no en días. Mientras lees esto, miles de empresas como la tuya ya están protegidas con monitoreo 24/7 impulsado por IA.</p>
        <p class="punch">⚡ 60 segundos para activar tu prueba gratuita</p>
      </div>
      <div class="ad-banner-cta">
        "><span class="cta-btn">#">QUIERO PROTEGER MI EMPRESA →</a>
        <span class="fine">Sin tarjeta de crédito · Cancela cuando quieras</span>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 1: OWASP TOP 10 ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 01 · Marco de referencia</span>
        <h2>OWASP Top 10 para Aplicaciones LLM</h2>
      </div>
      <div class="article-meta">Lectura: 6 min<br>Categoría: Seguridad de aplicaciones</div>
    </div>
    <div class="deck">El estándar que está ayudando a la industria a hablar el mismo idioma sobre riesgo en IA generativa.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          Cuando una organización integra un modelo de lenguaje en su producto, hereda una clase de vulnerabilidades
          que no existían en el desarrollo de software tradicional. Para ordenar ese panorama, la fundación OWASP
          publicó un listado específico de los diez riesgos más relevantes en aplicaciones basadas en LLM, pensado
          como guía práctica para equipos de desarrollo, arquitectura y seguridad.
        </p>
        <h4>Los riesgos que encabezan la lista</h4>
        <p>
          El listado abre con la inyección de prompts, donde una entrada cuidadosamente diseñada logra que el modelo
          ignore sus instrucciones originales. Le siguen el manejo inseguro de las salidas del modelo, que puede
          derivar en ejecución de código o en contenido malicioso mostrado al usuario final, y el envenenamiento de
          datos de entrenamiento, capaz de introducir sesgos o puertas traseras desde el origen del modelo.
        </p>
        <p>
          También aparecen la denegación de servicio por consumo de modelo, donde solicitudes diseñadas para ser
          extremadamente costosas agotan recursos de cómputo, y la divulgación de información sensible, un riesgo
          constante cuando el modelo fue entrenado o ajustado con datos privados que puede terminar repitiendo.
        </p>
        <h4>Por qué importa para equipos de desarrollo</h4>
        <p>
          Lo valioso de este marco no es solo la lista en sí, sino que ofrece un vocabulario común. Un equipo de
          ingeniería puede usarlo para priorizar pruebas de seguridad, un equipo de producto puede usarlo para
          justificar controles adicionales, y un equipo directivo puede usarlo para entender, en términos de negocio,
          qué significa exponer un asistente de IA a millones de usuarios sin las validaciones adecuadas.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Dato clave</div>
          <p>El marco se actualiza de forma periódica a medida que surgen nuevos patrones de ataque contra modelos en producción.</p>
        </div>
        <div class="box">
          <div class="label">Categorías destacadas</div>
          <ul>
            <li>Inyección de prompts</li>
            <li>Manejo inseguro de salidas</li>
            <li>Envenenamiento de datos</li>
            <li>Fuga de información sensible</li>
            <li>Dependencia excesiva del modelo</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ ANUNCIO 2 ============ -->
  <div class="ad-banner alt">
    <div class="ad-banner-inner">
      <div>
        <div class="ad-kicker">Computación en la nube</div>
        <h3>Migra a OrbitCloud antes<br>de que tu competencia lo haga.</h3>
        <p class="pitch">Cifrado de extremo a extremo, cumplimiento normativo automático y soporte humano real cuando lo necesites. Empresas que migraron este año ya reportan hasta 40% menos incidentes.</p>
        <p class="punch">🔥 Oferta de lanzamiento: 3 meses sin costo</p>
      </div>
      <div class="ad-banner-cta">
        "><span class="cta-btn">#">RESERVAR MI MIGRACIÓN →</a>
        <span class="fine">Plazas limitadas este mes</span>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 2: RIESGOS CRÍTICOS EN IA GENERATIVA ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 02 · Panorama de riesgo</span>
        <h2>Riesgos críticos en IA generativa</h2>
      </div>
      <div class="article-meta">Lectura: 5 min<br>Categoría: Gobernanza de IA</div>
    </div>
    <div class="deck">Más allá de la ciberseguridad técnica: los puntos ciegos que aparecen cuando un modelo genera contenido por sí solo.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          Hablar de riesgos en IA generativa implica ir más allá del código y entrar en el terreno del comportamiento
          del propio modelo. Uno de los problemas más persistentes es la alucinación: la capacidad de un sistema para
          producir información que suena coherente y autoritativa, pero que es simplemente falsa.
        </p>
        <p>
          A esto se suma el riesgo de fuga de datos sensibles. Si un modelo fue entrenado o ajustado con información
          interna de una empresa, existe la posibilidad de que esa información aparezca, parcial o completa, en una
          respuesta dirigida a un usuario que no debería tener acceso a ella.
        </p>
        <h4>Dependencia y pérdida de criterio</h4>
        <p>
          Otro riesgo, menos técnico pero igualmente serio, es la dependencia algorítmica: equipos que aceptan
          respuestas generadas sin verificación, erosionando con el tiempo la capacidad de juicio crítico dentro de
          la organización. Este fenómeno se vuelve particularmente delicado en sectores como salud, finanzas o
          derecho, donde una respuesta errónea puede tener consecuencias reales sobre personas.
        </p>
        <p>
          Finalmente está el riesgo reputacional y legal: contenido generado automáticamente que infringe derechos de
          autor, que reproduce sesgos discriminatorios, o que simplemente no refleja los valores de la marca que lo
          publica sin supervisión humana adecuada.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Riesgo silencioso</div>
          <p>La alucinación es peligrosa precisamente porque el modelo la presenta con el mismo tono de seguridad que una respuesta correcta.</p>
        </div>
        <div class="box">
          <div class="label">Mitigación recomendada</div>
          <ul>
            <li>Validación humana en decisiones críticas</li>
            <li>Trazabilidad de fuentes de entrenamiento</li>
            <li>Políticas claras de uso interno</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ ANUNCIO 4 ============ -->
  <div class="ad-banner alt">
    <div class="ad-banner-inner">
      <div>
        <div class="ad-kicker">Inteligencia Artificial</div>
        <h3>¿Tu IA dice cualquier cosa<br>cuando nadie la supervisa?</h3>
        <p class="pitch">Cortex Labs ajusta modelos de lenguaje a tu industria con controles de seguridad integrados desde el primer día. Lanza tu asistente de IA sin miedo a una alucinación costosa.</p>
        <p class="punch">🚀 Agenda una auditoría gratuita de tu modelo actual</p>
      </div>
      <div class="ad-banner-cta">
        "><span class="cta-btn">#">QUIERO MI AUDITORÍA →</a>
        <span class="fine">Cupos limitados esta semana</span>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 3: PROMPT INJECTION ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 03 · Amenaza emergente</span>
        <h2>Prompt Injection: el nuevo phishing de la era de la IA</h2>
      </div>
      <div class="article-meta">Lectura: 7 min<br>Categoría: Ataques dirigidos</div>
    </div>
    <div class="deck">No hace falta un correo sospechoso. Basta con un texto escondido donde el modelo lo lea.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          El phishing tradicional dependía de engañar a una persona. La inyección de prompts depende de engañar a un
          modelo. La lógica es parecida: un atacante introduce instrucciones disfrazadas dentro de un contenido que el
          sistema de IA va a procesar, ya sea un correo, una página web o un documento, con la intención de que el
          modelo las ejecute como si fueran órdenes legítimas del usuario.
        </p>
        <h4>Directa o indirecta</h4>
        <p>
          Existen dos variantes principales. La inyección directa ocurre cuando el propio usuario escribe instrucciones
          diseñadas para manipular al modelo y sortear sus reglas internas. La inyección indirecta, mucho más
          preocupante, ocurre cuando esas instrucciones llegan escondidas en una fuente externa que el modelo consulta,
          como una página web, un archivo adjunto o el resultado de una búsqueda, sin que el usuario lo sepa.
        </p>
        <p>
          Esta segunda variante es la que más preocupa a los equipos de seguridad, porque convierte cualquier
          asistente con capacidad de navegar, leer correos o ejecutar acciones en una potencial puerta de entrada:
          si el modelo confía ciegamente en el contenido que procesa, un atacante puede lograr que filtre datos, envíe
          mensajes no autorizados o tome decisiones dañinas sin que haya mediado ningún clic sospechoso por parte de
          la víctima.
        </p>
        <h4>Por qué se parece tanto al phishing</h4>
        <p>
          Igual que el phishing explotaba la confianza humana, la inyección de prompts explota la confianza del modelo
          en el texto que recibe. La diferencia es que aquí no hay forma de "capacitar" al sistema con la misma
          facilidad con la que se capacita a un empleado para reconocer un correo falso.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Vector de ataque</div>
          <p>Una página web, un PDF o un correo pueden contener instrucciones invisibles para el ojo humano pero perfectamente legibles para un modelo.</p>
        </div>
        <div class="box">
          <div class="label">Señal de alerta</div>
          <ul>
            <li>El asistente actúa fuera del contexto pedido</li>
            <li>Cambios repentinos de "personalidad" del modelo</li>
            <li>Solicitudes de datos que no venían del usuario</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ ANUNCIO 3 ============ -->
  <div class="ad-banner">
    <div class="ad-banner-inner">
      <div>
        <div class="ad-kicker">Software</div>
        <h3>Una sola contraseña filtrada<br>puede costarte todo.</h3>
        <p class="pitch">VaultLine Suite protege cada acceso de tu organización con autenticación adaptativa que aprende de cada intento de inicio de sesión. Implementación en menos de un día.</p>
        <p class="punch">✅ Prueba VaultLine gratis durante 14 días</p>
      </div>
      <div class="ad-banner-cta">
        "><span class="cta-btn">#">ACTIVAR PRUEBA GRATIS →</a>
        <span class="fine">Configuración guiada incluida</span>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 4: SEGURIDAD Y RIESGOS DE HERRAMIENTAS IA ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 04 · Adopción empresarial</span>
        <h2>Seguridad y riesgos de herramientas de IA generativa</h2>
      </div>
      <div class="article-meta">Lectura: 6 min<br>Categoría: Tecnología corporativa</div>
    </div>
    <div class="deck">La velocidad de adopción está superando, con frecuencia, la velocidad con la que se evalúan los riesgos.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          En menos de tres años, las herramientas de IA generativa pasaron de ser experimentos curiosos a estar
          integradas en los flujos de trabajo de equipos de marketing, soporte, desarrollo y recursos humanos. Esa
          velocidad de adopción trae beneficios evidentes en productividad, pero también una superficie de exposición
          que muchas empresas todavía no han cuantificado.
        </p>
        <h4>El problema del "shadow AI"</h4>
        <p>
          Una de las dinámicas más comunes es el uso no autorizado de herramientas de IA por parte de empleados que,
          sin mala intención, pegan información interna o de clientes en plataformas externas para resolver una tarea
          más rápido. A esta práctica se le conoce como shadow AI, y es equivalente al fenómeno del shadow IT que
          preocupó a los departamentos de tecnología durante años, pero con un agravante: los datos compartidos pueden
          quedar almacenados o usados para entrenar modelos de terceros.
        </p>
        <p>
          A nivel técnico, también existe el riesgo de integraciones mal configuradas: plugins, conectores o
          extensiones que otorgan a un modelo permisos más amplios de los que realmente necesita para cumplir su
          función, ampliando innecesariamente el impacto potencial de cualquier falla o ataque.
        </p>
        <h4>Gobernanza como respuesta</h4>
        <p>
          Las organizaciones que mejor están gestionando este riesgo no son necesariamente las que prohíben el uso de
          estas herramientas, sino las que han definido políticas claras: qué tipo de datos pueden compartirse, qué
          herramientas están aprobadas y qué nivel de supervisión humana se exige antes de publicar contenido generado
          automáticamente.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Concepto clave</div>
          <p><strong>Shadow AI:</strong> uso de herramientas de inteligencia artificial sin aprobación ni supervisión del área de seguridad de la organización.</p>
        </div>
        <div class="box">
          <div class="label">Buenas prácticas</div>
          <ul>
            <li>Catálogo interno de herramientas aprobadas</li>
            <li>Clasificación de datos antes de compartir</li>
            <li>Revisión periódica de permisos de plugins</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 5: CIBERDELINCUENTES Y IA ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 05 · Lado ofensivo</span>
        <h2>Cómo los ciberdelincuentes están utilizando inteligencia artificial</h2>
      </div>
      <div class="article-meta">Lectura: 7 min<br>Categoría: Cibercrimen</div>
    </div>
    <div class="deck">La misma tecnología que redacta correos de marketing ahora redacta campañas de phishing perfectas en segundos.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          Durante años, uno de los indicadores más confiables para detectar un correo de phishing era su mala
          redacción: errores gramaticales, traducciones torpes, formato extraño. La inteligencia artificial generativa
          eliminó esa ventaja. Hoy un atacante con conocimientos mínimos puede producir mensajes gramaticalmente
          perfectos, adaptados al tono corporativo exacto de la empresa que está suplantando.
        </p>
        <h4>Clonación de voz e identidad</h4>
        <p>
          Uno de los usos más alarmantes es la clonación de voz. Con apenas unos segundos de audio público, disponible
          en una entrevista, un video o una llamada previa, es posible generar un clip que imita la voz de una persona
          con suficiente fidelidad para engañar a un familiar o a un colega en una llamada de emergencia, una técnica
          que ya se ha usado en fraudes financieros dirigidos a empleados de áreas contables.
        </p>
        <p>
          A esto se suma el video sintético, capaz de simular videollamadas completas con la imagen y voz de un
          directivo, utilizado en esquemas donde se solicita una transferencia urgente de fondos durante una supuesta
          reunión.
        </p>
        <h4>Malware más adaptable</h4>
        <p>
          En el plano técnico, algunos grupos delictivos están explorando el uso de modelos de lenguaje para generar
          variantes de malware que cambian su propio código de forma automática, dificultando su detección por firmas
          tradicionales, y para automatizar la búsqueda de vulnerabilidades en sistemas expuestos a gran escala.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Caso de uso ofensivo</div>
          <p>Generación automatizada de campañas de phishing personalizadas a partir de información pública de la víctima.</p>
        </div>
        <div class="box">
          <div class="label">Tendencias observadas</div>
          <ul>
            <li>Clonación de voz para fraude telefónico</li>
            <li>Deepfakes en videollamadas corporativas</li>
            <li>Malware polimórfico asistido por IA</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ ANUNCIO 5 ============ -->
  <div class="ad-banner">
    <div class="ad-banner-inner">
      <div>
        <div class="ad-kicker">Educación tecnológica</div>
        <h3>En 12 semanas, conviértete<br>en el experto que tu equipo necesita.</h3>
        <p class="pitch">El diplomado de Academia Hexagon te enseña OWASP para LLM, respuesta a incidentes y arquitectura segura de IA, con mentoría en vivo. Cupos cerrando esta cohorte.</p>
        <p class="punch">🎓 Beca del 20% para los primeros 30 inscritos</p>
      </div>
      <div class="ad-banner-cta">
        "><span class="cta-btn">#">RESERVAR MI CUPO →</a>
        <span class="fine">Modalidad virtual · Certificación incluida</span>
      </div>
    </div>
  </div>

  <!-- ============ ARTÍCULO 6: IA PARA DEFENSA ============ -->
  <div class="section">
    <div class="article-head">
      <div>
        <span class="eyebrow">Artículo 06 · Lado defensivo</span>
        <h2>IA para la defensa en ciberseguridad</h2>
      </div>
      <div class="article-meta">Lectura: 6 min<br>Categoría: Defensa y respuesta</div>
    </div>
    <div class="deck">El mismo motor que potencia el ataque también está redefiniendo cómo se detecta y contiene una brecha.</div>
    <div class="article-body">
      <div class="col-text">
        <p>
          Si la inteligencia artificial amplió las capacidades ofensivas de los atacantes, también está transformando
          de forma profunda el trabajo de los equipos de defensa. Los centros de operaciones de seguridad, conocidos
          como SOC, reciben diariamente miles de alertas, y gran parte del valor de la IA en este contexto está en
          ayudar a priorizarlas.
        </p>
        <h4>Detección de anomalías a escala</h4>
        <p>
          Los modelos entrenados sobre patrones de comportamiento normal de una red pueden identificar desviaciones
          sutiles, un usuario que accede a sistemas fuera de su horario habitual, un volumen de tráfico inusual hacia
          una región geográfica nueva, mucho antes de que esas señales se conviertan en un incidente confirmado.
        </p>
        <p>
          Esta capacidad es particularmente valiosa frente a amenazas que evolucionan rápido, donde las firmas de
          detección tradicionales no logran mantenerse al día. Un modelo bien entrenado no necesita conocer la firma
          exacta de un ataque para sospechar de un comportamiento que se aleja de lo esperado.
        </p>
        <h4>Respuesta asistida y no autónoma</h4>
        <p>
          Una tendencia importante es el uso de asistentes de IA dentro del propio SOC, capaces de resumir un
          incidente complejo en lenguaje natural, sugerir los siguientes pasos de contención y redactar el reporte
          posterior, liberando tiempo del analista humano para las decisiones que realmente requieren su criterio.
          La discusión más sana en este campo no es si automatizar, sino qué decisiones deben permanecer siempre bajo
          supervisión humana directa.
        </p>
      </div>
      <div class="sidebar">
        <div class="box">
          <div class="label">Aplicación práctica</div>
          <p>Sistemas de detección de anomalías que aprenden el comportamiento normal de una red para identificar desviaciones sutiles.</p>
        </div>
        <div class="box">
          <div class="label">Principio rector</div>
          <ul>
            <li>La IA acelera la detección</li>
            <li>El criterio humano decide la respuesta</li>
            <li>La trazabilidad de cada acción es obligatoria</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ============ COLOFÓN ============ -->
  <div class="colophon">
    <span>SENTINEL · Revista Digital de IA y Ciberseguridad · Edición 02, 2026</span>
    <span>Preparado por: Cesar Maure</span>
  </div>

</div>
</body>
</html>
