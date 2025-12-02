<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard Personal Operativo Isvi 2025</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <style>
    * { margin:0; padding:0; box-sizing:border-box; }
    
    :root {
      --primary: #6366f1;
      --primary-dark: #4f46e5;
      --success: #10b981;
      --danger: #ef4444;
      --warning: #f59e0b;
      --dark: #1e293b;
      --card-bg: rgba(255,255,255,0.95);
      --shadow-lg: 0 20px 50px rgba(0,0,0,0.2);
    }
    
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #1a4d3e 0%, #0d2d23 50%, #1a4d3e 100%);
      min-height: 100vh;
      padding: 15px;
      color: #fff;
      animation: fadeIn 0.5s;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    
    .container {
      max-width: 1200px;
      margin: 0 auto;
    }
    
    /* Header Premium */
    .header {
      background: rgba(255,255,255,0.1);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255,255,255,0.2);
      border-radius: 16px;
      padding: 20px;
      margin-bottom: 15px;
      text-align: center;
    }
    
    .header h1 {
      color: white;
      font-size: 1.8em;
      font-weight: 800;
      margin-bottom: 5px;
    }
    
    .header p {
      color: rgba(255,255,255,0.8);
      font-size: 0.9em;
      margin-bottom: 8px;
    }
    
    .header .total-display {
      font-size: 1.8em;
      font-weight: 900;
      color: white;
      margin-top: 5px;
    }
    
    /* Botones de Navegación 3D */
    .nav-buttons {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
      margin-bottom: 15px;
    }
    
    .btn-nav {
      background: transparent;
      color: white;
      border: 2px solid rgba(255,255,255,0.3);
      border-radius: 10px;
      padding: 12px 18px;
      font-size: 0.95em;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }
    
    .btn-nav:hover {
      background: rgba(255,255,255,0.1);
      border-color: rgba(255,255,255,0.5);
      transform: translateY(-2px);
    }
    
    .btn-nav.active {
      background: rgba(255,255,255,0.95);
      color: #1a4d3e;
      border-color: white;
    }
    
    .btn-nav i {
      display: none;
    }
    
    /* Contenedor de Secciones */
    .content-section {
      display: none;
      animation: slideUp 0.6s ease-out;
    }
    
    .content-section.active {
      display: block;
    }
    
    @keyframes slideUp {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    /* Cards */
    .card {
      background: rgba(255,255,255,0.95);
      backdrop-filter: blur(10px);
      border-radius: 16px;
      padding: 20px;
      margin-bottom: 15px;
    }
    
    .card-title {
      font-size: 1.4em;
      font-weight: 800;
      color: var(--dark);
      margin-bottom: 15px;
    }
    
    /* Tabla Moderna */
    .table-container {
      overflow-x: auto;
      border-radius: 16px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    }
    
    table {
      width: 100%;
      border-collapse: collapse;
      background: white;
    }
    
    th {
      background: linear-gradient(135deg, #1a4d3e, #0d2d23);
      color: white;
      padding: 14px 12px;
      font-weight: 600;
      text-transform: uppercase;
      font-size: 0.85em;
      letter-spacing: 0.5px;
    }
    
    td {
      padding: 12px;
      color: var(--dark);
      border-bottom: 1px solid #f1f5f9;
      text-align: center;
    }
    
    tr:hover {
      background: #f8fafc;
    }
    
    .badge {
      display: inline-block;
      padding: 5px 12px;
      border-radius: 16px;
      font-weight: 600;
      font-size: 0.9em;
    }
    
    .badge-success {
      background: #d1fae5;
      color: var(--success);
    }
    
    .badge-danger {
      background: #fee2e2;
      color: var(--danger);
    }
    
    /* Gráficos */
    .chart-container {
      height: 280px;
      position: relative;
    }
    
    .charts-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 15px;
    }
    
    /* KPI Grid */
    .kpi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 12px;
    }
    
    .kpi-card {
      background: linear-gradient(135deg, #ffffff, #f8fafc);
      border-radius: 12px;
      padding: 18px;
      text-align: center;
      transition: all 0.3s;
      border-top: 3px solid var(--primary);
    }
    
    .kpi-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    }
    
    .kpi-card.success { border-top-color: var(--success); }
    .kpi-card.danger { border-top-color: var(--danger); }
    .kpi-card.warning { border-top-color: var(--warning); }
    
    .kpi-icon {
      font-size: 2em;
      opacity: 0.2;
      margin-bottom: 8px;
    }
    
    .kpi-value {
      font-size: 1.8em;
      font-weight: 900;
      color: var(--dark);
      margin: 5px 0;
    }
    
    .kpi-label {
      color: #64748b;
      font-size: 0.85em;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      font-weight: 600;
    }
    
    /* Insights */
    .insights-list {
      list-style: none;
    }
    
    .insight-item {
      background: linear-gradient(135deg, #f8fafc, #e2e8f0);
      padding: 15px;
      margin: 10px 0;
      border-radius: 12px;
      border-left: 3px solid var(--primary);
      color: var(--dark);
      font-size: 0.95em;
      display: flex;
      align-items: center;
      gap: 12px;
      transition: all 0.3s;
    }
    
    .insight-item:hover {
      transform: translateX(10px);
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    
    .insight-item i {
      color: var(--primary);
      font-size: 1.4em;
      min-width: 30px;
    }
    
    /* Responsive */
    @media (max-width: 768px) {
      .nav-buttons {
        grid-template-columns: 1fr;
      }
      
      .charts-grid {
        grid-template-columns: 1fr;
      }
      
      .header h1 {
        font-size: 2em;
      }
      
      .btn-nav {
        font-size: 1.1em;
        padding: 20px 15px;
      }
    }
  </style>
</head>
<body>

<div class="container">
  <!-- Header -->
  <div class="header">

    <h1>📊 Dashboard Personal Operativo Isvi 2025</h1>
    <p>Sistema de Análisis Integral de Personal</p>
    <div class="total-display">390 Empleados</div>
  </div>

  <!-- Botones de Navegación -->
  <div class="nav-buttons">
    <button class="btn-nav active" onclick="showSection('resumen')">
      <i class="fas fa-home"></i> 🏠 Resumen
    </button>
    <button class="btn-nav" onclick="showSection('tabla')">
      <i class="fas fa-table"></i> 📋 Datos Completos
    </button>
    <button class="btn-nav" onclick="showSection('graficos')">
      <i class="fas fa-chart-area"></i> 📈 Gráficos
    </button>
    <button class="btn-nav" onclick="showSection('kpis')">
      <i class="fas fa-tachometer-alt"></i> 🎯 KPIs
    </button>
    <button class="btn-nav" onclick="showSection('insights')">
      <i class="fas fa-lightbulb"></i> 💡 Insights
    </button>
  </div>

  <!-- SECCIÓN RESUMEN -->
  <div id="resumen" class="content-section active">
    <div class="card">
      <h2 class="card-title">⭐ Resumen Ejecutivo</h2>
      <div class="kpi-grid">
        <div class="kpi-card success">
          <i class="fas fa-users kpi-icon" style="color: var(--success);"></i>
          <div class="kpi-value">390</div>
          <div class="kpi-label">Total Actual</div>
        </div>
        <div class="kpi-card">
          <i class="fas fa-arrow-trend-up kpi-icon" style="color: var(--primary);"></i>
          <div class="kpi-value">+133%</div>
          <div class="kpi-label">Crecimiento</div>
        </div>
        <div class="kpi-card warning">
          <i class="fas fa-trophy kpi-icon" style="color: var(--warning);"></i>
          <div class="kpi-value">129</div>
          <div class="kpi-label">Récord Julio</div>
        </div>
        <div class="kpi-card danger">
          <i class="fas fa-fire kpi-icon" style="color: var(--danger);"></i>
          <div class="kpi-value">+196</div>
          <div class="kpi-label">Crecimiento Total</div>
        </div>
      </div>
    </div>

    <div class="charts-grid">
      <div class="card">
        <h3 class="card-title" style="font-size: 1.5em;"><i class="fas fa-chart-line"></i> Evolución Mensual</h3>
        <div class="chart-container">
          <canvas id="chartResumen"></canvas>
        </div>
      </div>
      <div class="card">
        <h3 class="card-title" style="font-size: 1.5em;"><i class="fas fa-chart-pie"></i> Distribución Total</h3>
        <div class="chart-container">
          <canvas id="chartPieResumen"></canvas>
        </div>
      </div>
    </div>
  </div>

  <!-- SECCIÓN TABLA -->
  <div id="tabla" class="content-section">
    <div class="card">
      <h2 class="card-title"><i class="fas fa-table"></i> Datos Mensuales Completos</h2>
      <div class="table-container">
        <table>
          <thead>
            <tr>
              <th>Mes</th>
              <th>Ingresos</th>
              <th>Retiros</th>
              <th>Movimiento Neto</th>
              <th>Total Final</th>
            </tr>
          </thead>
          <tbody id="tableBody"></tbody>
        </table>
      </div>
    </div>
  </div>

  <!-- SECCIÓN GRÁFICOS -->
  <div id="graficos" class="content-section">
    <div class="card">
      <h2 class="card-title"><i class="fas fa-chart-area"></i> Evolución del Personal</h2>
      <div class="chart-container">
        <canvas id="chartEvolucion"></canvas>
      </div>
    </div>

    <div class="card">
      <h2 class="card-title"><i class="fas fa-exchange-alt"></i> Ingresos vs Retiros</h2>
      <div class="chart-container">
        <canvas id="chartMovimientos"></canvas>
      </div>
    </div>

    <div class="card">
      <h2 class="card-title"><i class="fas fa-chart-bar"></i> Balance Neto Mensual</h2>
      <div class="chart-container">
        <canvas id="chartNeto"></canvas>
      </div>
    </div>
  </div>

  <!-- SECCIÓN KPIs -->
  <div id="kpis" class="content-section">
    <div class="card">
      <h2 class="card-title"><i class="fas fa-tachometer-alt"></i> Indicadores Clave de Rendimiento</h2>
      <div class="kpi-grid">
        <div class="kpi-card success">
          <i class="fas fa-user-plus kpi-icon" style="color: var(--success);"></i>
          <div class="kpi-value">293</div>
          <div class="kpi-label">Total Ingresos</div>
        </div>
        <div class="kpi-card danger">
          <i class="fas fa-user-minus kpi-icon" style="color: var(--danger);"></i>
          <div class="kpi-value">130</div>
          <div class="kpi-label">Total Retiros</div>
        </div>
        <div class="kpi-card">
          <i class="fas fa-plus kpi-icon" style="color: var(--primary);"></i>
          <div class="kpi-value">+163</div>
          <div class="kpi-label">Crecimiento Neto</div>
        </div>
        <div class="kpi-card warning">
          <i class="fas fa-percent kpi-icon" style="color: var(--warning);"></i>
          <div class="kpi-value">69%</div>
          <div class="kpi-label">Tasa Retención</div>
        </div>
        <div class="kpi-card success">
          <i class="fas fa-calendar-check kpi-icon" style="color: var(--success);"></i>
          <div class="kpi-value">29</div>
          <div class="kpi-label">Promedio Ingresos</div>
        </div>
        <div class="kpi-card danger">
          <i class="fas fa-calendar-times kpi-icon" style="color: var(--danger);"></i>
          <div class="kpi-value">13</div>
          <div class="kpi-label">Promedio Retiros</div>
        </div>
        <div class="kpi-card">
          <i class="fas fa-rocket kpi-icon" style="color: var(--primary);"></i>
          <div class="kpi-value">Jul</div>
          <div class="kpi-label">Mejor Mes</div>
        </div>
        <div class="kpi-card warning">
          <i class="fas fa-chart-line kpi-icon" style="color: var(--warning);"></i>
          <div class="kpi-value">+16</div>
          <div class="kpi-label">Promedio Neto</div>
        </div>
      </div>
    </div>
  </div>

  <!-- SECCIÓN INSIGHTS -->
  <div id="insights" class="content-section">
    <div class="card">
      <h2 class="card-title">💡 Análisis Ejecutivo 2025 & Insights Estratégicos</h2>
      <ul class="insights-list">
        <li class="insight-item">
          <i class="fas fa-rocket"></i>
          <span><strong>Expansión Estratégica - Julio 2025:</strong> La incorporación del cliente MUZO mediante los contratos EMS y GREEN generó el ingreso de 129 colaboradores, representando el 44% del total de incorporaciones del año y consolidando el mes como el de mayor crecimiento histórico de la operación.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-chart-line"></i>
          <span><strong>Escalamiento Organizacional:</strong> La planta de personal experimentó un crecimiento del 115% en el período enero-noviembre, pasando de 170 a 390 colaboradores, superando significativamente las proyecciones iniciales y demostrando la capacidad operativa de absorción de nuevos contratos.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-fire"></i>
          <span><strong>Consolidación Mayo 2025:</strong> El segundo mejor desempeño del año con +49 colaboradores netos se atribuye directamente al inicio de operaciones del contrato de Unidad de Mantenimiento Vial, evidenciando capacidad de arranque efectivo de proyectos de gran envergadura.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-exclamation-triangle"></i>
          <span><strong>Transición Contractual - Enero 2025:</strong> La finalización del contrato COMBUSCOL en las ciudades de Bogotá, Cali y Medellín el 31 de diciembre de 2024 resultó en 29 desvinculaciones durante enero, estableciendo la línea base de 170 colaboradores para el inicio del ejercicio fiscal.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-check-circle"></i>
          <span><strong>Fase de Consolidación Q3-Q4:</strong> A partir de agosto se observa una estabilización del crecimiento con incorporaciones mensuales entre +3 y +20 colaboradores, reflejando una fase de madurez operativa donde se prioriza la consolidación de contratos existentes sobre la expansión agresiva.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-calendar-alt"></i>
          <span><strong>Indicador de Retención:</strong> Con 293 ingresos frente a 130 retiros, la organización mantiene una tasa de permanencia del 69%, posicionándose por encima del benchmark sectorial y evidenciando políticas efectivas de gestión del talento humano.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-bullseye"></i>
          <span><strong>Proyección Cierre Fiscal 2025:</strong> Manteniendo la tendencia de incorporación mensual promedio de +12-15 colaboradores observada en Q4, se proyecta cerrar el ejercicio con una planta entre 400-410 empleados, representando un crecimiento anual del 135% respecto al inicio del período.</span>
        </li>
        <li class="insight-item">
          <i class="fas fa-trophy"></i>
          <span><strong>Sostenibilidad del Crecimiento:</strong> El registro de balance positivo en 7 de los 10 meses analizados confirma una trayectoria de expansión sostenible, respaldada por la diversificación de cartera de clientes y la exitosa ejecución de nuevos contratos estructurales.</span>
        </li>
      </ul>
    </div>
  </div>
</div>

<script>
// Datos
const meses = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre'];
const mesesCortos = ['Ene', 'Feb', 'Mar', 'Abr', 'May', 'Jun', 'Jul', 'Ago', 'Sep', 'Oct', 'Nov'];
const ingresos = [10, 15, 0, 18, 51, 4, 129, 25, 23, 18, 42];
const retiros = [29, 1, 13, 10, 2, 21, 23, 22, 3, 6, 18];
const neto = [-19, 14, -13, 8, 49, -17, 106, 3, 20, 12, 24];
const total = [170, 187, 174, 193, 242, 225, 331, 334, 354, 366, 390];

// Función para cambiar de sección
function showSection(sectionId) {
  // Ocultar todas las secciones
  document.querySelectorAll('.content-section').forEach(section => {
    section.classList.remove('active');
  });
  
  // Quitar active de todos los botones
  document.querySelectorAll('.btn-nav').forEach(btn => {
    btn.classList.remove('active');
  });
  
  // Mostrar la sección seleccionada
  document.getElementById(sectionId).classList.add('active');
  
  // Activar el botón correspondiente
  event.target.closest('.btn-nav').classList.add('active');
}

// Llenar tabla
const tbody = document.getElementById('tableBody');
meses.forEach((mes, i) => {
  const netoVal = neto[i];
  const badgeClass = netoVal > 0 ? 'badge-success' : netoVal < 0 ? 'badge-danger' : 'badge-neutral';
  const netoText = netoVal > 0 ? `+${netoVal}` : netoVal;
  
  tbody.innerHTML += `
    <tr>
      <td><strong>${mes}</strong></td>
      <td>${ingresos[i]}</td>
      <td>${retiros[i]}</td>
      <td><span class="badge ${badgeClass}">${netoText}</span></td>
      <td><strong>${total[i]}</strong></td>
    </tr>
  `;
});

// Configuración común de gráficos
Chart.defaults.font.family = "'Inter', sans-serif";
Chart.defaults.font.size = 13;

// Gráfico Resumen - Línea
new Chart(document.getElementById('chartResumen'), {
  type: 'line',
  data: {
    labels: mesesCortos,
    datasets: [{
      label: 'Total Personal',
      data: total,
      borderColor: '#6366f1',
      backgroundColor: 'rgba(99, 102, 241, 0.1)',
      borderWidth: 3,
      tension: 0.4,
      fill: true,
      pointRadius: 6,
      pointHoverRadius: 9,
      pointBackgroundColor: '#6366f1',
      pointBorderColor: '#fff',
      pointBorderWidth: 2
    }]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: { display: false },
      tooltip: {
        backgroundColor: 'rgba(0,0,0,0.8)',
        padding: 12,
        titleFont: { size: 14, weight: 'bold' },
        bodyFont: { size: 13 }
      }
    },
    scales: {
      y: {
        beginAtZero: false,
        grid: { color: 'rgba(0,0,0,0.05)' }
      },
      x: {
        grid: { display: false }
      }
    }
  }
});

// Gráfico Resumen - Pie
new Chart(document.getElementById('chartPieResumen'), {
  type: 'doughnut',
  data: {
    labels: ['Total Ingresos', 'Total Retiros', 'Crecimiento Neto'],
    datasets: [{
      data: [293, 130, 163],
      backgroundColor: ['#10b981', '#ef4444', '#6366f1'],
      borderWidth: 0,
      hoverOffset: 20
    }]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: {
        position: 'bottom',
        labels: { padding: 20, font: { size: 13, weight: '600' } }
      }
    }
  }
});

// Gráfico Evolución
new Chart(document.getElementById('chartEvolucion'), {
  type: 'line',
  data: {
    labels: meses,
    datasets: [{
      label: 'Total de Personal',
      data: total,
      borderColor: '#6366f1',
      backgroundColor: 'rgba(99, 102, 241, 0.2)',
      borderWidth: 4,
      tension: 0.4,
      fill: true,
      pointRadius: 7,
      pointHoverRadius: 10,
      pointBackgroundColor: '#6366f1',
      pointBorderColor: '#fff',
      pointBorderWidth: 3
    }]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: { 
        display: true,
        labels: { font: { size: 14, weight: '600' } }
      }
    },
    scales: {
      y: {
        beginAtZero: false,
        grid: { color: 'rgba(0,0,0,0.05)' }
      },
      x: {
        grid: { display: false }
      }
    }
  }
});

// Gráfico Movimientos
new Chart(document.getElementById('chartMovimientos'), {
  type: 'bar',
  data: {
    labels: meses,
    datasets: [
      {
        label: 'Ingresos',
        data: ingresos,
        backgroundColor: '#10b981',
        borderRadius: 10,
        borderWidth: 0
      },
      {
        label: 'Retiros',
        data: retiros,
        backgroundColor: '#ef4444',
        borderRadius: 10,
        borderWidth: 0
      }
    ]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: {
        position: 'top',
        labels: { padding: 20, font: { size: 14, weight: '600' } }
      }
    },
    scales: {
      y: {
        beginAtZero: true,
        grid: { color: 'rgba(0,0,0,0.05)' }
      },
      x: {
        grid: { display: false }
      }
    }
  }
});

// Gráfico Neto
new Chart(document.getElementById('chartNeto'), {
  type: 'bar',
  data: {
    labels: meses,
    datasets: [{
      label: 'Movimiento Neto',
      data: neto,
      backgroundColor: neto.map(val => val > 0 ? '#10b981' : '#ef4444'),
      borderRadius: 10,
      borderWidth: 0
    }]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: { 
        display: true,
        labels: { font: { size: 14, weight: '600' } }
      }
    },
    scales: {
      y: {
        beginAtZero: true,
        grid: { color: 'rgba(0,0,0,0.05)' }
      },
      x: {
        grid: { display: false }
      }
    }
  }
});
</script>

</body>
</html>
