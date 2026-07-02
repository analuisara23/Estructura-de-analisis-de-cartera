<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Indicadores Clave — Cartera Corporativa Jetstereo</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#F5F6F8; --surface:#FFFFFF; --border:#E3E6EB; --border-strong:#CBD1DA;
    --text:#1B2430; --text-dim:#68707C;
    --blue:#1E5FA8; --blue-dark:#123B6B; --blue-bg:#EAF1FA;
    --green:#2E7D53; --green-bg:rgba(46,125,83,.09);
    --amber:#A9791C; --amber-bg:rgba(169,121,28,.09);
    --red:#B23B2E; --red-bg:rgba(178,59,46,.08);
    --gray-badge:#5B6472; --gray-badge-bg:rgba(91,100,114,.08);
  }
  *{box-sizing:border-box;margin:0;padding:0}
  body{background:var(--bg);color:var(--text);font-family:'Inter',sans-serif;line-height:1.6;-webkit-font-smoothing:antialiased}
  em{font-style:normal;color:var(--blue)}
  .wrapper{max-width:1080px;margin:0 auto;padding:48px 32px 80px}

  .header{padding-bottom:28px;border-bottom:1px solid var(--border);margin-bottom:8px}
  .header-eyebrow{font-family:'DM Mono',monospace;font-size:12px;letter-spacing:.1em;text-transform:uppercase;color:var(--blue);margin-bottom:14px}
  .header h1{font-size:36px;font-weight:700;letter-spacing:-0.01em}
  .header-sub{margin-top:8px;font-size:15px;color:var(--text-dim)}
  .version-badge{margin-top:18px;display:inline-flex;align-items:center;gap:8px;background:var(--blue-bg);color:var(--blue-dark);border:1px solid #CFE0F2;padding:6px 14px;border-radius:20px;font-family:'DM Mono',monospace;font-size:12px}
  .version-badge .dot{width:7px;height:7px;border-radius:50%;background:var(--blue)}

  .tabs{display:flex;gap:4px;margin:32px 0 32px;border-bottom:1px solid var(--border);flex-wrap:wrap}
  .tab-btn{font-family:'Inter',sans-serif;font-size:14px;font-weight:500;color:var(--text-dim);background:none;border:none;padding:12px 18px;cursor:pointer;position:relative;top:1px}
  .tab-btn:hover{color:var(--text)}
  .tab-btn.active{color:var(--blue);border-bottom:2px solid var(--blue)}
  .tab-panel{display:none}
  .tab-panel.active{display:block;animation:fade .25s ease}
  @keyframes fade{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:translateY(0)}}

  .section-label{font-family:'DM Mono',monospace;font-size:11px;letter-spacing:.08em;text-transform:uppercase;color:var(--text-dim);margin-bottom:20px}

  /* KPI RESUMEN */
  .kpi-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:14px}
  .kpi-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:22px 22px 20px}
  .kpi-value{font-family:'DM Mono',monospace;font-size:30px;font-weight:500;color:var(--border-strong)}
  .kpi-label{margin-top:4px;font-size:14.5px;font-weight:600;color:var(--text)}
  .kpi-context{margin-top:8px;font-size:12.5px;color:var(--text-dim)}
  .kpi-cat{margin-top:14px}

  /* CARDS */
  .card-grid{display:flex;flex-direction:column;gap:14px}
  .card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:22px 24px}
  .card-head{display:flex;justify-content:space-between;align-items:flex-start;gap:16px;flex-wrap:wrap}
  .ind-name{font-size:16.5px;font-weight:600}
  .def{margin-top:6px;font-size:14px;color:var(--text-dim);max-width:640px}

  .badge{font-family:'DM Mono',monospace;font-size:11px;padding:5px 12px;border-radius:20px;white-space:nowrap;display:inline-flex;align-items:center;gap:6px}
  .badge-chart{background:var(--blue-bg);color:var(--blue-dark);border:1px solid #CFE0F2}
  .badge-gray{background:var(--gray-badge-bg);color:var(--gray-badge);border:1px solid var(--border-strong)}

  .card-foot{margin-top:16px;padding-top:14px;border-top:1px dashed var(--border);display:flex;flex-direction:column;gap:10px}
  .row-label{font-family:'DM Mono',monospace;font-size:11px;color:var(--text-dim);text-transform:uppercase;letter-spacing:.06em;margin-bottom:4px}
  .col-tag{font-family:'DM Mono',monospace;font-size:12px;color:var(--blue-dark);background:var(--blue-bg);padding:2px 8px;border-radius:4px;display:inline-block;margin:2px 4px 2px 0}
  .why-text{font-size:13.5px;color:var(--text-dim)}
  .importa-text{font-size:13.5px;color:var(--text)}

  /* METODOLOGÍA — OPCIONES DE NIVEL DE RIESGO */
  .method-options{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px}
  .method-card{border:1px solid var(--border);border-radius:12px;padding:18px 20px 20px;background:#FAFBFC;border-top:3px solid var(--border-strong)}
  .method-card.tier-1{border-top-color:var(--gray-badge)}
  .method-card.tier-2{border-top-color:var(--blue)}
  .method-card.tier-3{border-top-color:var(--green)}
  .method-tier{font-family:'DM Mono',monospace;font-size:10.5px;letter-spacing:.06em;text-transform:uppercase;color:var(--text-dim)}
  .method-name{font-size:15px;font-weight:700;margin-top:4px}
  .method-row{margin-top:11px;font-size:12.5px}
  .method-row .ml{font-family:'DM Mono',monospace;font-size:10.5px;text-transform:uppercase;letter-spacing:.05em;color:var(--text-dim);display:block;margin-bottom:3px}
  .method-row .mv{color:var(--text)}
  .method-row .mv.dim{color:var(--text-dim)}

  .method-example{
    margin-top:16px;background:#fff;border:1px dashed var(--border-strong);border-radius:8px;padding:12px 14px;
  }
  .tier-1 .method-example{border-color:rgba(91,100,114,.35)}
  .tier-2 .method-example{border-color:rgba(30,95,168,.3);background:var(--blue-bg)}
  .tier-3 .method-example{border-color:rgba(46,125,83,.3);background:var(--green-bg)}
  .method-example .ex-head{
    display:flex;align-items:center;gap:6px;font-family:'DM Mono',monospace;font-size:10px;
    text-transform:uppercase;letter-spacing:.05em;color:var(--text-dim);margin-bottom:6px;
  }
  .method-example .ex-head::before{content:'✎';font-size:12px}
  .method-example .ex-body{font-size:12.5px;color:var(--text);line-height:1.55}
  .method-example .ex-note{margin-top:6px;font-size:10.5px;color:var(--text-dim);font-style:italic}

  @media (max-width:640px){.wrapper{padding:32px 18px 60px}.header h1{font-size:28px}}
</style>
</head>
<body>

<div class="wrapper">

  <div class="header">
    <div class="header-eyebrow">Estrategia de Cobranza Corporativa · Jetstereo</div>
    <h1>Indicadores <em>Clave</em></h1>
    <div class="header-sub">Cartera corporativa · De lo general a lo granular</div>
    <div class="version-badge"><span class="dot"></span> Línea base · Validada con BI Analyst</div>
  </div>

  <div class="tabs">
    <button class="tab-btn active" onclick="switchTab('resumen')">Resumen General</button>
    <button class="tab-btn" onclick="switchTab('riesgo')">Calidad de Cartera y Riesgo</button>
    <button class="tab-btn" onclick="switchTab('comercial')">Desempeño Comercial</button>
    <button class="tab-btn" onclick="switchTab('pago')">Pago y Concentración</button>
  </div>

  <!-- ══════════════ TAB: RESUMEN ══════════════ -->
  <div id="tab-resumen" class="tab-panel active">
    <div class="section-label">Página 1 del dashboard · Solo cifras exactas, sin desagregar aún</div>
    <div class="kpi-grid">
      <div class="kpi-card">
        <div class="kpi-value">—</div>
        <div class="kpi-label">Saldo total de cartera corporativa</div>
        <div class="kpi-context">Punto de partida: referencia de tamaño para leer todo lo demás en contexto.</div>
        <div class="kpi-cat badge badge-gray">Calidad</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-value">—</div>
        <div class="kpi-label">% de mora</div>
        <div class="kpi-context">Primera señal de alerta ejecutiva sobre la salud de la cartera.</div>
        <div class="kpi-cat badge badge-gray">Calidad</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-value">—</div>
        <div class="kpi-label">Cobertura de reserva</div>
        <div class="kpi-context">¿Estamos financieramente protegidos frente al riesgo vencido actual?</div>
        <div class="kpi-cat badge badge-gray">Calidad</div>
      </div>
      <div class="kpi-card">
        <div class="kpi-value">—</div>
        <div class="kpi-label">% de cartera en Top 10 clientes</div>
        <div class="kpi-context">Qué tan expuesta está la institución a un puñado de nombres.</div>
        <div class="kpi-cat badge badge-gray">Concentración</div>
      </div>
    </div>
  </div>

  <!-- ══════════════ TAB: RIESGO ══════════════ -->
  <div id="tab-riesgo" class="tab-panel">
    <div class="section-label">Página 2 del dashboard · ¿Qué tan sana está la cartera corporativa hoy?</div>
    <div class="card-grid">

      <div class="card">
        <div class="card-head">
          <div class="ind-name">% de mora</div>
          <div class="badge badge-chart">KPI + tendencia mensual</div>
        </div>
        <div class="def">Proporción del riesgo total en atraso</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Primera señal de alerta: si sube, activa revisión de buckets y de los clientes que la explican.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Total riesgo vencido</span><span class="col-tag">Total riesgo</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Necesita verse mes a mes — si sube o baja importa más que el valor puntual.</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Distribución por bucket de mora</div>
          <div class="badge badge-chart">Barras apiladas</div>
        </div>
        <div class="def">Cartera agrupada por rango de días de atraso</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Muestra si la mora se concentra en atrasos tempranos (recuperable) o se desliza a buckets críticos (pérdida probable).</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Bucket de mora</span><span class="col-tag">Saldo capital</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Muestra el "deslizamiento" de mora entre rangos — tema priorizado en el kickoff.</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Cobertura de reserva</div>
          <div class="badge badge-chart">Medidor (gauge) con umbral</div>
        </div>
        <div class="def">Nivel de protección de la reserva frente al riesgo vencido</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Mide si la institución está protegida financieramente, no solo cuánto se debe.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Reserva</span><span class="col-tag">Total riesgo vencido</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Es un indicador de "¿estamos cubiertos o no?" — el gauge lo comunica en un vistazo.</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Cartera por nivel de riesgo</div>
          <div class="badge badge-chart">Dona</div>
        </div>
        <div class="badge" style="background:var(--amber-bg);color:var(--amber);border:1px solid rgba(169,121,28,.2);margin-top:8px">⚠ Pendiente de metodología para corporativo</div>
        <div class="def" style="margin-top:10px">Distribución del saldo según clasificación de riesgo — Bajo / Medio / Alto / Muy Alto</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Suele anticipar el deterioro antes de que se vuelva mora real.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Nivel de riesgo</span><span class="col-tag">Saldo capital</span></div>
          <div><div class="row-label">Brecha detectada</div><div class="importa-text"><code>Nivel de riesgo</code> existe para retail pero no está calibrado para corporativo — el campo saldría vacío. Abajo están las tres rutas posibles, de la más simple a la que debería ser el objetivo técnico.</div></div>
        </div>

        <div class="row-label" style="margin-top:18px">Opciones de segmentación — de lo simple a lo ideal</div>
        <div class="method-options">

          <div class="method-card tier-1">
            <div class="method-tier">Opción 1 · Simple</div>
            <div class="method-name">Reglas fijas</div>
            <div class="method-row"><span class="ml">Qué es</span><span class="mv">Bajo/Medio/Alto/Muy Alto asignado por combinaciones directas de mora, estado de crédito y cobertura de reserva.</span></div>
            <div class="method-row"><span class="ml">Ventaja</span><span class="mv">Se construye ya, con los datos disponibles hoy.</span></div>
            <div class="method-row"><span class="ml">Limitación</span><span class="mv dim">Reactivo — mide mora que ya ocurrió, no la anticipa.</span></div>
            <div class="method-row"><span class="ml">Responsable</span><span class="mv dim">BI, con reglas definidas por negocio.</span></div>
            <div class="method-example">
              <div class="ex-head">Ejemplo</div>
              <div class="ex-body">Cliente con <strong>45 días de mora</strong> y <strong>cobertura de reserva de 40%</strong> → clasifica <strong>"Alto"</strong> por regla directa.</div>
              <div class="ex-note">Ilustrativo, no calibrado con datos reales.</div>
            </div>
          </div>

          <div class="method-card tier-2">
            <div class="method-tier">Opción 2 · Intermedio</div>
            <div class="method-name">Scorecard ponderado</div>
            <div class="method-row"><span class="ml">Qué es</span><span class="mv">Score 0-100 combinando mora, tendencia de mora, cobertura de reserva, avance de pago y antigüedad, cada una con un peso.</span></div>
            <div class="method-row"><span class="ml">Ventaja</span><span class="mv">Pondera varias señales a la vez — más preciso que una regla fija.</span></div>
            <div class="method-row"><span class="ml">Limitación</span><span class="mv dim">Los pesos se definen por juicio experto, no estadísticamente.</span></div>
            <div class="method-row"><span class="ml">Responsable</span><span class="mv dim">Data Science, validado por Riesgo.</span></div>
            <div class="method-example">
              <div class="ex-head">Ejemplo</div>
              <div class="ex-body">Score = (mora×0.4) + (tendencia×0.2) + (cobertura×0.2) + (avance de pago×0.2) = <strong>62/100</strong> → banda <strong>"Medio"</strong>.</div>
              <div class="ex-note">Pesos (0.4/0.2/0.2/0.2) solo para ilustrar la mecánica, no una propuesta.</div>
            </div>
          </div>

          <div class="method-card tier-3">
            <div class="method-tier">Opción 3 · Objetivo técnico</div>
            <div class="method-name">PD por matrices de transición</div>
            <div class="method-row"><span class="ml">Qué es</span><span class="mv">Probabilidad de incumplimiento calibrada con matrices de transición — misma metodología ya validada para la cartera de Gobierno.</span></div>
            <div class="method-row"><span class="ml">Ventaja</span><span class="mv">Predictivo, no reactivo, y da consistencia metodológica entre segmentos.</span></div>
            <div class="method-row"><span class="ml">Limitación</span><span class="mv dim">Requiere historial de default corporativo suficiente para calibrar.</span></div>
            <div class="method-row"><span class="ml">Responsable</span><span class="mv dim">Data Science (Emmanuel), validado por Riesgo.</span></div>
            <div class="method-example">
              <div class="ex-head">Ejemplo</div>
              <div class="ex-body">Cliente "al día" con probabilidad histórica de pasar a mora en 30 días ≈ <strong>8% mensual</strong> → PD acumulada a 3 meses ≈ <strong>22%</strong> → banda <strong>"Alto"</strong>.</div>
              <div class="ex-note">Ilustra la lógica de una matriz de transición — no es un dato real de tu cartera.</div>
            </div>
          </div>

        </div>
      </div>

    </div>
  </div>

  <!-- ══════════════ TAB: COMERCIAL ══════════════ -->
  <div id="tab-comercial" class="tab-panel">
    <div class="section-label">Página 3 del dashboard · ¿Está creciendo la cartera corporativa, y dónde?</div>
    <div class="card-grid">

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Contratos nuevos por período</div>
          <div class="badge badge-chart">Serie de tiempo (línea)</div>
        </div>
        <div class="def">Volumen de contratos nuevos originados en el mes</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Mide si el negocio corporativo está creciendo o se está estancando en volumen de colocación.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Numero de contrato</span><span class="col-tag">Fecha de originacion</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">La pregunta es de tendencia: ¿colocamos más o menos que el mes pasado?</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Colocación por región, zona y tienda</div>
          <div class="badge badge-chart">Barras horizontales</div>
        </div>
        <div class="def">Distribución geográfica y por punto de venta de la colocación corporativa</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Identifica qué regiones, zonas y tiendas puntuales concentran el crecimiento y cuáles quedan rezagadas frente al plan comercial — el nivel de tienda permite bajar la conversación de "la región" a un punto de venta específico.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Region</span><span class="col-tag">Zona comercial</span><span class="col-tag">Techo tienda</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Muchas categorías con nombres largos — el ranking horizontal es más legible que un mapa, y permite filtrar de región a tienda sin cambiar de visual.</div></div>
        </div>
      </div>

    </div>
  </div>

  <!-- ══════════════ TAB: PAGO Y CONCENTRACIÓN ══════════════ -->
  <div id="tab-pago" class="tab-panel">
    <div class="section-label">Página 4 del dashboard · ¿Dónde se concentra la exposición y quién se está atrasando?</div>
    <div class="card-grid">

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Top clientes por exposición</div>
          <div class="badge badge-chart">Ranking horizontal (top 10-20)</div>
        </div>
        <div class="def">Clientes corporativos con mayor riesgo total</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Un solo cliente grande en problemas puede mover el indicador de mora total — hay que saber quiénes son.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Codigo de cliente</span><span class="col-tag">Total riesgo</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Formato estándar para "quién concentra más riesgo", fácil de escanear.</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Concentración por sector</div>
          <div class="badge badge-chart">Treemap</div>
        </div>
        <div class="def">Exposición de cartera por sector económico y actividad</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Un sector económico en crisis puede arrastrar a varios clientes corporativos a la vez.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Sector Industrial</span><span class="col-tag">Actividad economica</span><span class="col-tag">Saldo capital</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Muchos sectores con pesos muy distintos — el área comunica proporción mejor que barras.</div></div>
        </div>
      </div>

      <div class="card">
        <div class="card-head">
          <div class="ind-name">Avance de pago</div>
          <div class="badge badge-chart">Barra de progreso / histograma</div>
        </div>
        <div class="def">Proporción de cuotas ya pagadas sobre el plazo total</div>
        <div class="card-foot">
          <div><div class="row-label">Por qué importa</div><div class="importa-text">Detecta contratos que se están atrasando en su plan de pago antes de que aparezcan como mora formal.</div></div>
          <div><div class="row-label">Fuente</div><span class="col-tag">Cuotas pagadas</span><span class="col-tag">Plazo</span></div>
          <div><div class="row-label">Por qué este gráfico</div><div class="why-text">Es una métrica de avance — la barra de progreso es el lenguaje visual más directo.</div></div>
        </div>
      </div>

    </div>
  </div>

</div>

<script>
  function switchTab(name){
    document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
    document.querySelectorAll('.tab-panel').forEach(p=>p.classList.remove('active'));
    document.querySelector(`.tab-btn[onclick="switchTab('${name}')"]`).classList.add('active');
    document.getElementById(`tab-${name}`).classList.add('active');
  }
</script>

</body>
</html>
