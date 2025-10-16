<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Congreso Hospitalario 2025</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Open+Sans:wght@400;600&family=Roboto+Mono&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/FileSaver.js/2.0.5/FileSaver.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mammoth/1.6.0/mammoth.browser.min.js"></script>
    <style>
        :root {
            --primary-blue: #1a4a7a;
            --secondary-blue: #2c6aa4;
            --white: #ffffff;
            --light-gray: #f8f9fa;
            --medium-gray: #e9ecef;
            --dark-gray: #495057;
            --success-green: #28a745;
            --alert-red: #dc3545;
            --countdown-orange: #fd7e14;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.6;
            color: var(--dark-gray);
            background-color: var(--light-gray);
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        /* Header & Navigation */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo-placeholder {
            width: 60px;
            height: 60px;
            background-color: var(--primary-blue);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }

        .logo-text h1 {
            font-size: 1.2rem;
            margin-bottom: 0.2rem;
        }

        .logo-text p {
            font-size: 0.9rem;
            color: var(--dark-gray);
        }

        .admin-login-btn {
            background-color: var(--secondary-blue);
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            cursor: pointer;
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            transition: background-color 0.3s;
        }

        .admin-login-btn:hover {
            background-color: var(--primary-blue);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--secondary-blue) 100%);
            color: white;
            padding: 3rem 0;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .badge {
            background-color: rgba(255,255,255,0.2);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: 600;
        }

        .countdown {
            font-family: 'Roboto Mono', monospace;
            font-size: 1.5rem;
            margin-bottom: 2rem;
            background-color: rgba(0,0,0,0.2);
            padding: 1rem;
            border-radius: 8px;
            display: inline-block;
        }

        .cta-button {
            background-color: var(--countdown-orange);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 4px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .cta-button:hover {
            background-color: #e06616;
        }

        .cta-button:disabled {
            background-color: var(--medium-gray);
            color: var(--dark-gray);
            cursor: not-allowed;
        }

        /* Information Cards */
        .info-section {
            padding: 3rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--primary-blue);
        }

        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .card {
            background-color: var(--white);
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            padding: 1.5rem;
            text-align: center;
        }

        .card i {
            font-size: 2rem;
            color: var(--secondary-blue);
            margin-bottom: 1rem;
        }

        .card h3 {
            color: var(--primary-blue);
            margin-bottom: 0.5rem;
        }

        /* Registration Section */
        .registration-section {
            padding: 3rem 0;
            background-color: var(--white);
        }

        .registration-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: var(--light-gray);
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--medium-gray);
            border-radius: 4px;
            font-family: 'Open Sans', sans-serif;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: var(--secondary-blue);
        }

        .registration-status {
            text-align: center;
            margin-bottom: 1.5rem;
            padding: 1rem;
            border-radius: 4px;
        }

        .status-open {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success-green);
            border: 1px solid var(--success-green);
        }

        .status-closed {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--alert-red);
            border: 1px solid var(--alert-red);
        }

        .status-limited {
            background-color: rgba(253, 126, 20, 0.1);
            color: var(--countdown-orange);
            border: 1px solid var(--countdown-orange);
        }

        .slots-info {
            margin-top: 1rem;
            font-size: 0.9rem;
            color: var(--dark-gray);
        }

        /* Agenda & Certificates Section */
        .agenda-certificates {
            padding: 3rem 0;
        }

        .agenda-container, .certificates-container {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
            text-align: center;
        }

        .agenda-status, .certificates-status {
            margin: 1rem 0;
            padding: 1rem;
            border-radius: 4px;
            font-weight: 600;
        }

        .status-pending {
            background-color: rgba(253, 126, 20, 0.1);
            color: var(--countdown-orange);
        }

        .status-available {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success-green);
        }

        .download-btn {
            background-color: var(--secondary-blue);
            color: white;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: background-color 0.3s;
        }

        .download-btn:hover {
            background-color: var(--primary-blue);
        }

        .download-btn:disabled {
            background-color: var(--medium-gray);
            color: var(--dark-gray);
            cursor: not-allowed;
        }

        /* Footer */
        footer {
            background-color: var(--primary-blue);
            color: white;
            padding: 2rem 0;
            text-align: center;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        /* Admin Panel Styles */
        .admin-panel {
            display: none;
            padding: 2rem 0;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid var(--medium-gray);
        }

        .admin-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            border-bottom: 1px solid var(--medium-gray);
        }

        .admin-tab {
            padding: 0.75rem 1.5rem;
            background: none;
            border: none;
            border-bottom: 3px solid transparent;
            cursor: pointer;
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
            color: var(--dark-gray);
            transition: all 0.3s;
        }

        .admin-tab.active {
            color: var(--primary-blue);
            border-bottom-color: var(--primary-blue);
        }

        .admin-tab-content {
            display: none;
        }

        .admin-tab-content.active {
            display: block;
        }

        .dashboard-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background-color: var(--white);
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            text-align: center;
        }

        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--dark-gray);
            font-size: 0.9rem;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            border-radius: 8px;
            overflow: hidden;
        }

        .data-table th, .data-table td {
            padding: 1rem;
            text-align: left;
            border-bottom: 1px solid var(--medium-gray);
        }

        .data-table th {
            background-color: var(--primary-blue);
            color: white;
            font-weight: 600;
        }

        .data-table tr:last-child td {
            border-bottom: none;
        }

        .action-btn {
            background: none;
            border: none;
            cursor: pointer;
            margin-right: 0.5rem;
            color: var(--secondary-blue);
        }

        .action-btn.delete {
            color: var(--alert-red);
        }

        .search-box {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--medium-gray);
            border-radius: 4px;
            margin-bottom: 1rem;
        }

        .file-upload-area {
            border: 2px dashed var(--medium-gray);
            border-radius: 8px;
            padding: 2rem;
            text-align: center;
            margin-bottom: 1rem;
            cursor: pointer;
            transition: all 0.3s;
        }

        .file-upload-area:hover {
            border-color: var(--secondary-blue);
            background-color: rgba(44, 106, 164, 0.05);
        }

        .file-upload-area i {
            font-size: 3rem;
            color: var(--secondary-blue);
            margin-bottom: 1rem;
        }

        .attendance-status {
            display: inline-block;
            padding: 0.25rem 0.5rem;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .status-approved {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success-green);
        }

        .status-pending {
            background-color: rgba(253, 126, 20, 0.1);
            color: var(--countdown-orange);
        }

        .status-reproved {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--alert-red);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h2 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .countdown {
                font-size: 1.2rem;
            }
            
            .admin-tabs {
                flex-wrap: wrap;
            }
            
            .admin-tab {
                flex: 1;
                min-width: 120px;
                text-align: center;
            }
            
            .data-table {
                display: block;
                overflow-x: auto;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-container">
                    <div class="logo-placeholder">
                        <i class="fas fa-hospital"></i>
                    </div>
                    <div class="logo-text">
                        <h1>Hospital ULEAM</h1>
                        <p>Congreso Médico 2025</p>
                    </div>
                </div>
                <button class="admin-login-btn" id="adminLoginBtn">
                    <i class="fas fa-lock"></i> Acceso Admin
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h2>Congreso de Actualización Médica 2025</h2>
                <p>Avances y tendencias en medicina moderna</p>
                
                <div class="badges">
                    <div class="badge">GRATUITO</div>
                    <div class="badge">CUPOS LIMITADOS: 220</div>
                </div>
                
                <div class="countdown" id="countdown">
                    <span id="days">00</span>d <span id="hours">00</span>h <span id="minutes">00</span>m <span id="seconds">00</span>s
                </div>
                
                <button class="cta-button" id="registerButton">Registrarse Ahora</button>
            </div>
        </div>
    </section>

    <!-- Information Section -->
    <section class="info-section">
        <div class="container">
            <h2 class="section-title">Información del Evento</h2>
            <div class="cards-container">
                <div class="card">
                    <i class="fas fa-calendar-alt"></i>
                    <h3>Fechas</h3>
                    <p>23-25 Octubre 2025</p>
                </div>
                <div class="card">
                    <i class="fas fa-map-marker-alt"></i>
                    <h3>Ubicación</h3>
                    <p>Auditorio ULEAM</p>
                    <p>Manta, Ecuador</p>
                </div>
                <div class="card">
                    <i class="fas fa-users"></i>
                    <h3>Capacidad</h3>
                    <p>220 cupos totales</p>
                    <p id="availableSlotsInfo">50 disponibles para médicos</p>
                </div>
                <div class="card">
                    <i class="fas fa-certificate"></i>
                    <h3>Certificados</h3>
                    <p>Requieren 2/3 asistencias</p>
                    <p>Disponibles: 25-Oct, 13:00</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Registration Section -->
    <section class="registration-section">
        <div class="container">
            <h2 class="section-title">Registro de Participantes</h2>
            <div class="registration-form">
                <div id="registrationStatus" class="registration-status status-open">
                    <i class="fas fa-check-circle"></i> Inscripciones Abiertas
                </div>
                
                <form id="registrationForm">
                    <div class="form-group">
                        <label for="title">Título</label>
                        <select id="title" name="title" required>
                            <option value="">Seleccione</option>
                            <option value="DR.">DR.</option>
                            <option value="DRA.">DRA.</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="firstName">Nombres</label>
                        <input type="text" id="firstName" name="firstName" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="lastName">Apellidos</label>
                        <input type="text" id="lastName" name="lastName" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Correo Electrónico</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="category">Categoría</label>
                        <select id="category" name="category" required>
                            <option value="">Seleccione</option>
                            <option value="DR./DRA. Médico General">DR./DRA. Médico General</option>
                            <option value="DR./DRA. Especialista">DR./DRA. Especialista</option>
                            <option value="Licenciado Enfermería">Licenciado Enfermería</option>
                            <option value="Internos">Internos</option>
                        </select>
                    </div>
                    
                    <div class="slots-info" id="slotsInfo">
                        Cupos disponibles para médicos: <span id="medicalSlots">50</span>
                    </div>
                    
                    <button type="submit" class="cta-button" id="submitRegistration">Completar Registro</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Agenda & Certificates Section -->
    <section class="agenda-certificates">
        <div class="container">
            <div class="agenda-container">
                <h2>Agenda del Congreso</h2>
                <div class="agenda-status status-pending">
                    <i class="fas fa-clock"></i> Próximamente
                </div>
                <button class="download-btn" id="downloadAgenda" disabled>
                    <i class="fas fa-download"></i> Descargar Agenda
                </button>
            </div>
            
            <div class="certificates-container">
                <h2>Certificados de Participación</h2>
                <div class="certificates-status status-pending">
                    <i class="fas fa-clock"></i> Disponibles a partir del 25-Oct-2025, 13:00
                </div>
                <p>Requisito: Mínimo 2 de 3 asistencias registradas</p>
                <button class="download-btn" id="downloadCertificate" disabled>
                    <i class="fas fa-download"></i> Descargar Certificado
                </button>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>Congreso de Actualización Médica 2025 - Hospital ULEAM</p>
            <p>Auditorio ULEAM, Manta, Ecuador | 23-25 Octubre 2025</p>
        </div>
    </footer>

    <!-- Admin Login Modal -->
    <div class="modal" id="adminLoginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Acceso Administrativo</h3>
                <button class="close-modal">&times;</button>
            </div>
            <form id="adminLoginForm">
                <div class="form-group">
                    <label for="adminUsername">Usuario</label>
                    <input type="text" id="adminUsername" name="adminUsername" required>
                </div>
                <div class="form-group">
                    <label for="adminPassword">Contraseña</label>
                    <input type="password" id="adminPassword" name="adminPassword" required>
                </div>
                <button type="submit" class="cta-button">Ingresar</button>
            </form>
        </div>
    </div>

    <!-- Admin Panel -->
    <div class="admin-panel" id="adminPanel">
        <div class="container">
            <div class="admin-header">
                <h2>Panel de Administración</h2>
                <button class="admin-login-btn" id="logoutBtn">
                    <i class="fas fa-sign-out-alt"></i> Cerrar Sesión
                </button>
            </div>
            
            <div class="admin-tabs">
                <button class="admin-tab active" data-tab="participants">Gestión de Participantes</button>
                <button class="admin-tab" data-tab="agenda">Gestión de Agenda</button>
                <button class="admin-tab" data-tab="attendance">Control de Asistencias</button>
                <button class="admin-tab" data-tab="certificates">Generación de Certificados</button>
            </div>
            
            <!-- Participants Management Tab -->
            <div class="admin-tab-content active" id="participants-tab">
                <h3>Gestión de Participantes</h3>
                
                <div class="dashboard-stats">
                    <div class="stat-card">
                        <div class="stat-value" id="totalSlots">220</div>
                        <div class="stat-label">Cupos Totales</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="assignedSlots">0</div>
                        <div class="stat-label">Cupos Asignados</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="availableSlots">220</div>
                        <div class="stat-label">Cupos Disponibles</div>
                    </div>
                </div>
                
                <div class="form-group">
                    <input type="text" class="search-box" id="participantSearch" placeholder="Buscar participantes...">
                </div>
                
                <button class="cta-button" id="addParticipantBtn">
                    <i class="fas fa-plus"></i> Agregar Participante
                </button>
                
                <button class="download-btn" id="exportParticipantsBtn">
                    <i class="fas fa-file-export"></i> Exportar a CSV
                </button>
                
                <table class="data-table" id="participantsTable">
                    <thead>
                        <tr>
                            <th>Nombre</th>
                            <th>Email</th>
                            <th>Categoría</th>
                            <th>Fecha Registro</th>
                            <th>Acciones</th>
                        </tr>
                    </thead>
                    <tbody id="participantsTableBody">
                        <!-- Participants will be populated here -->
                    </tbody>
                </table>
            </div>
            
            <!-- Agenda Management Tab -->
            <div class="admin-tab-content" id="agenda-tab">
                <h3>Gestión de Agenda</h3>
                
                <div class="file-upload-area" id="agendaUploadArea">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Arrastra y suelta el archivo de agenda aquí o haz clic para seleccionar</p>
                    <p><small>Formato permitido: PDF (máximo 20MB)</small></p>
                    <input type="file" id="agendaFile" accept=".pdf" style="display: none;">
                </div>
                
                <div id="agendaPreview" style="display: none;">
                    <h4>Vista Previa de Agenda</h4>
                    <div id="agendaPreviewContent"></div>
                    <button class="cta-button" id="publishAgendaBtn">
                        <i class="fas fa-check"></i> Publicar Agenda
                    </button>
                </div>
            </div>
            
            <!-- Attendance Control Tab -->
            <div class="admin-tab-content" id="attendance-tab">
                <h3>Control de Asistencias</h3>
                
                <div class="form-group">
                    <label for="attendanceDay">Día del Congreso</label>
                    <select id="attendanceDay">
                        <option value="day1">Día 1 (23 Oct)</option>
                        <option value="day2">Día 2 (24 Oct)</option>
                        <option value="day3">Día 3 (25 Oct)</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="googleFormLink">Enlace de Google Forms</label>
                    <input type="url" id="googleFormLink" placeholder="https://forms.google.com/...">
                    <button class="download-btn" id="saveFormLinkBtn">Guardar Enlace</button>
                </div>
                
                <button class="cta-button" id="syncAttendanceBtn">
                    <i class="fas fa-sync"></i> Sincronizar Asistencias
                </button>
                
                <button class="download-btn" id="exportAttendanceBtn">
                    <i class="fas fa-file-export"></i> Exportar Consolidado
                </button>
                
                <table class="data-table" id="attendanceTable">
                    <thead>
                        <tr>
                            <th>Participante</th>
                            <th>Día 1</th>
                            <th>Día 2</th>
                            <th>Día 3</th>
                            <th>Estado</th>
                        </tr>
                    </thead>
                    <tbody id="attendanceTableBody">
                        <!-- Attendance data will be populated here -->
                    </tbody>
                </table>
            </div>
            
            <!-- Certificates Generation Tab -->
            <div class="admin-tab-content" id="certificates-tab">
                <h3>Generación de Certificados</h3>
                
                <div class="file-upload-area" id="certificateTemplateUploadArea">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Arrastra y suelta la plantilla de certificado aquí o haz clic para seleccionar</p>
                    <p><small>Formato permitido: Word (.docx) con campos: {{cargo}}, {{apellido}}, {{nombre}}</small></p>
                    <input type="file" id="certificateTemplateFile" accept=".docx" style="display: none;">
                </div>
                
                <div id="certificatePreview" style="display: none;">
                    <h4>Vista Previa de Certificado</h4>
                    <div id="certificatePreviewContent"></div>
                    
                    <div style="margin-top: 1rem;">
                        <button class="cta-button" id="generateAllCertificatesBtn">
                            <i class="fas fa-certificate"></i> Generar Todos los Certificados
                        </button>
                        
                        <button class="download-btn" id="downloadCertificatesZipBtn">
                            <i class="fas fa-file-archive"></i> Descargar Todos (ZIP)
                        </button>
                    </div>
                </div>
                
                <div style="margin-top: 2rem;">
                    <h4>Certificados para No Inscritos</h4>
                    <button class="cta-button" id="generateExternalCertificateBtn">
                        <i class="fas fa-user-plus"></i> Generar Certificado Externo
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Estado global de la aplicación
        const AppState = {
            // Estados del sistema
            REGISTRATION: {
                OPEN: 'Inscripciones Abiertas',
                CLOSED: 'Inscripciones Cerradas',
                LIMITED: 'Cupos Limitados'
            },
            ATTENDANCE: {
                PENDING: 'Pendiente',
                APPROVED: 'Aprobado',
                REPROVED: 'No Aprobado'
            },
            CERTIFICATES: {
                UNAVAILABLE: 'No Disponible',
                AVAILABLE: 'Descargar',
                PENDING: 'Pendiente de Asistencia'
            },
            
            // Datos iniciales
            participants: [],
            slots: {
                total: 220,
                categories: {
                    'DR./DRA. Médico General': 25,
                    'DR./DRA. Especialista': 25,
                    'Licenciado Enfermería': 100,
                    'Internos': 70
                },
                assigned: {
                    'DR./DRA. Médico General': 0,
                    'DR./DRA. Especialista': 0,
                    'Licenciado Enfermería': 0,
                    'Internos': 0
                }
            },
            agenda: null,
            attendance: {},
            certificateTemplate: null,
            adminSession: null,
            
            // Participante demo
            DEMO_PARTICIPANT: {
                cargo: 'DR.',
                nombre: 'Prueba',
                apellido: 'Prueba',
                email: 'demo@hospital.com',
                categoria: 'Especialista',
                fechaRegistro: new Date().toISOString()
            }
        };

        // Inicialización cuando el DOM está listo
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
            setupEventListeners();
            updateCountdown();
            setInterval(updateCountdown, 1000);
            checkRegistrationStatus();
            updateSlotsInfo();
        });

        // Inicializar la aplicación
        function initializeApp() {
            // Cargar datos del localStorage
            loadFromLocalStorage();
            
            // Agregar participante demo si no hay datos
            if (AppState.participants.length === 0) {
                AppState.participants.push(AppState.DEMO_PARTICIPANT);
                AppState.slots.assigned['DR./DRA. Especialista'] = 1;
                saveToLocalStorage();
            }
            
            // Actualizar la UI
            updateParticipantsTable();
            updateAttendanceTable();
            updateDashboardStats();
        }

        // Configurar event listeners
        function setupEventListeners() {
            // Botón de acceso admin
            document.getElementById('adminLoginBtn').addEventListener('click', showAdminLoginModal);
            
            // Cerrar modal
            document.querySelector('.close-modal').addEventListener('click', hideAdminLoginModal);
            
            // Login admin
            document.getElementById('adminLoginForm').addEventListener('submit', handleAdminLogin);
            
            // Cerrar sesión
            document.getElementById('logoutBtn').addEventListener('click', handleAdminLogout);
            
            // Tabs del admin panel
            document.querySelectorAll('.admin-tab').forEach(tab => {
                tab.addEventListener('click', function() {
                    switchAdminTab(this.dataset.tab);
                });
            });
            
            // Formulario de registro
            document.getElementById('registrationForm').addEventListener('submit', handleRegistration);
            
            // Botón de registro desde hero
            document.getElementById('registerButton').addEventListener('click', function() {
                document.getElementById('registrationForm').scrollIntoView({ behavior: 'smooth' });
            });
            
            // Búsqueda de participantes
            document.getElementById('participantSearch').addEventListener('input', filterParticipants);
            
            // Agregar participante
            document.getElementById('addParticipantBtn').addEventListener('click', showAddParticipantModal);
            
            // Exportar participantes
            document.getElementById('exportParticipantsBtn').addEventListener('click', exportParticipantsToCSV);
            
            // Subir agenda
            document.getElementById('agendaUploadArea').addEventListener('click', function() {
                document.getElementById('agendaFile').click();
            });
            
            document.getElementById('agendaFile').addEventListener('change', handleAgendaUpload);
            
            // Sincronizar asistencias
            document.getElementById('syncAttendanceBtn').addEventListener('click', syncAttendance);
            
            // Exportar asistencias
            document.getElementById('exportAttendanceBtn').addEventListener('click', exportAttendanceToCSV);
            
            // Subir plantilla de certificados
            document.getElementById('certificateTemplateUploadArea').addEventListener('click', function() {
                document.getElementById('certificateTemplateFile').click();
            });
            
            document.getElementById('certificateTemplateFile').addEventListener('change', handleCertificateTemplateUpload);
            
            // Generar certificados
            document.getElementById('generateAllCertificatesBtn').addEventListener('click', generateAllCertificates);
        }

        // Contador regresivo
        function updateCountdown() {
            const targetDate = new Date('2025-10-23T00:00:00').getTime();
            const now = new Date().getTime();
            const difference = targetDate - now;
            
            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);
                
                document.getElementById('days').textContent = days.toString().padStart(2, '0');
                document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
                document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
                document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
            } else {
                document.getElementById('countdown').textContent = '¡El congreso ha comenzado!';
            }
        }

        // Verificar estado de registro
        function checkRegistrationStatus() {
            const now = new Date();
            const deadline = new Date('2025-10-22T23:59:59');
            const statusElement = document.getElementById('registrationStatus');
            const submitButton = document.getElementById('submitRegistration');
            const registerButton = document.getElementById('registerButton');
            
            if (now > deadline) {
                // Fuera de fecha
                statusElement.className = 'registration-status status-closed';
                statusElement.innerHTML = '<i class="fas fa-times-circle"></i> Inscripciones Cerradas';
                submitButton.disabled = true;
                submitButton.textContent = 'Inscripciones Cerradas';
                registerButton.disabled = true;
                registerButton.textContent = 'Inscripciones Cerradas';
            } else {
                // Dentro de fecha
                const medicalSlotsAvailable = AppState.slots.categories['DR./DRA. Médico General'] + 
                                            AppState.slots.categories['DR./DRA. Especialista'] - 
                                            AppState.slots.assigned['DR./DRA. Médico General'] - 
                                            AppState.slots.assigned['DR./DRA. Especialista'];
                
                if (medicalSlotsAvailable <= 0) {
                    // Cupos agotados
                    statusElement.className = 'registration-status status-closed';
                    statusElement.innerHTML = '<i class="fas fa-times-circle"></i> Cupos Agotados para Médicos';
                    submitButton.disabled = true;
                    submitButton.textContent = 'No Disponible';
                    registerButton.disabled = true;
                    registerButton.textContent = 'No Disponible';
                } else {
                    // Cupos disponibles
                    statusElement.className = 'registration-status status-open';
                    statusElement.innerHTML = '<i class="fas fa-check-circle"></i> Inscripciones Abiertas';
                    submitButton.disabled = false;
                    submitButton.textContent = 'Completar Registro';
                    registerButton.disabled = false;
                    registerButton.textContent = 'Registrarse Ahora';
                }
            }
        }

        // Actualizar información de cupos
        function updateSlotsInfo() {
            const medicalSlotsAvailable = AppState.slots.categories['DR./DRA. Médico General'] + 
                                        AppState.slots.categories['DR./DRA. Especialista'] - 
                                        AppState.slots.assigned['DR./DRA. Médico General'] - 
                                        AppState.slots.assigned['DR./DRA. Especialista'];
            
            document.getElementById('medicalSlots').textContent = medicalSlotsAvailable;
            document.getElementById('availableSlotsInfo').textContent = `${medicalSlotsAvailable} disponibles para médicos`;
        }

        // Manejar registro de participantes
        function handleRegistration(event) {
            event.preventDefault();
            
            const formData = new FormData(event.target);
            const title = formData.get('title');
            const firstName = formData.get('firstName');
            const lastName = formData.get('lastName');
            const email = formData.get('email');
            const category = formData.get('category');
            
            // Verificar disponibilidad de cupos
            if (category === 'DR./DRA. Médico General' || category === 'DR./DRA. Especialista') {
                const assigned = AppState.slots.assigned[category];
                const available = AppState.slots.categories[category];
                
                if (assigned >= available) {
                    alert('Lo sentimos, no hay cupos disponibles para esta categoría.');
                    return;
                }
            } else {
                alert('Solo se permiten registros para médicos generales o especialistas.');
                return;
            }
            
            // Crear nuevo participante
            const newParticipant = {
                cargo: title,
                nombre: firstName,
                apellido: lastName,
                email: email,
                categoria: category,
                fechaRegistro: new Date().toISOString(),
                asistencias: {
                    day1: false,
                    day2: false,
                    day3: false
                }
            };
            
            // Agregar a la lista
            AppState.participants.push(newParticipant);
            AppState.slots.assigned[category]++;
            
            // Guardar en localStorage
            saveToLocalStorage();
            
            // Actualizar UI
            updateParticipantsTable();
            updateDashboardStats();
            updateSlotsInfo();
            checkRegistrationStatus();
            
            // Limpiar formulario
            event.target.reset();
            
            // Mostrar confirmación
            alert('¡Registro exitoso! Te hemos enviado un correo de confirmación.');
        }

        // Mostrar modal de login admin
        function showAdminLoginModal() {
            document.getElementById('adminLoginModal').style.display = 'flex';
        }

        // Ocultar modal de login admin
        function hideAdminLoginModal() {
            document.getElementById('adminLoginModal').style.display = 'none';
            document.getElementById('adminLoginForm').reset();
        }

        // Manejar login admin
        function handleAdminLogin(event) {
            event.preventDefault();
            
            const formData = new FormData(event.target);
            const username = formData.get('adminUsername');
            const password = formData.get('adminPassword');
            
            if (username === 'DOCENCIA' && password === 'DOCENCIA') {
                // Crear sesión admin
                AppState.adminSession = {
                    username: username,
                    loginTime: new Date().toISOString()
                };
                
                // Guardar sesión en sessionStorage
                sessionStorage.setItem('adminSession', JSON.stringify(AppState.adminSession));
                
                // Mostrar panel admin
                document.getElementById('adminPanel').style.display = 'block';
                document.querySelector('header').style.display = 'none';
                document.querySelector('.hero').style.display = 'none';
                document.querySelector('.info-section').style.display = 'none';
                document.querySelector('.registration-section').style.display = 'none';
                document.querySelector('.agenda-certificates').style.display = 'none';
                document.querySelector('footer').style.display = 'none';
                
                // Ocultar modal
                hideAdminLoginModal();
                
                // Configurar timeout de sesión (30 minutos)
                setTimeout(handleAdminLogout, 30 * 60 * 1000);
            } else {
                alert('Credenciales incorrectas. Usuario: DOCENCIA, Contraseña: DOCENCIA');
            }
        }

        // Manejar logout admin
        function handleAdminLogout() {
            AppState.adminSession = null;
            sessionStorage.removeItem('adminSession');
            
            // Ocultar panel admin
            document.getElementById('adminPanel').style.display = 'none';
            
            // Mostrar contenido público
            document.querySelector('header').style.display = 'block';
            document.querySelector('.hero').style.display = 'block';
            document.querySelector('.info-section').style.display = 'block';
            document.querySelector('.registration-section').style.display = 'block';
            document.querySelector('.agenda-certificates').style.display = 'block';
            document.querySelector('footer').style.display = 'block';
        }

        // Cambiar tab en panel admin
        function switchAdminTab(tabName) {
            // Desactivar todos los tabs
            document.querySelectorAll('.admin-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.querySelectorAll('.admin-tab-content').forEach(content => {
                content.classList.remove('active');
            });
            
            // Activar tab seleccionado
            document.querySelector(`.admin-tab[data-tab="${tabName}"]`).classList.add('active');
            document.getElementById(`${tabName}-tab`).classList.add('active');
        }

        // Actualizar tabla de participantes
        function updateParticipantsTable() {
            const tableBody = document.getElementById('participantsTableBody');
            tableBody.innerHTML = '';
            
            AppState.participants.forEach((participant, index) => {
                const row = document.createElement('tr');
                
                row.innerHTML = `
                    <td>${participant.cargo} ${participant.nombre} ${participant.apellido}</td>
                    <td>${participant.email}</td>
                    <td>${participant.categoria}</td>
                    <td>${new Date(participant.fechaRegistro).toLocaleDateString()}</td>
                    <td>
                        <button class="action-btn edit" data-index="${index}">
                            <i class="fas fa-edit"></i>
                        </button>
                        <button class="action-btn delete" data-index="${index}">
                            <i class="fas fa-trash"></i>
                        </button>
                    </td>
                `;
                
                tableBody.appendChild(row);
            });
            
            // Agregar event listeners a los botones de acción
            document.querySelectorAll('.action-btn.edit').forEach(btn => {
                btn.addEventListener('click', function() {
                    const index = this.dataset.index;
                    editParticipant(index);
                });
            });
            
            document.querySelectorAll('.action-btn.delete').forEach(btn => {
                btn.addEventListener('click', function() {
                    const index = this.dataset.index;
                    deleteParticipant(index);
                });
            });
        }

        // Filtrar participantes
        function filterParticipants() {
            const searchTerm = document.getElementById('participantSearch').value.toLowerCase();
            const rows = document.querySelectorAll('#participantsTableBody tr');
            
            rows.forEach(row => {
                const text = row.textContent.toLowerCase();
                row.style.display = text.includes(searchTerm) ? '' : 'none';
            });
        }

        // Actualizar estadísticas del dashboard
        function updateDashboardStats() {
            const totalAssigned = Object.values(AppState.slots.assigned).reduce((a, b) => a + b, 0);
            
            document.getElementById('totalSlots').textContent = AppState.slots.total;
            document.getElementById('assignedSlots').textContent = totalAssigned;
            document.getElementById('availableSlots').textContent = AppState.slots.total - totalAssigned;
        }

        // Editar participante
        function editParticipant(index) {
            const participant = AppState.participants[index];
            // En una implementación completa, aquí se mostraría un modal de edición
            alert(`Editar participante: ${participant.nombre} ${participant.apellido}`);
        }

        // Eliminar participante
        function deleteParticipant(index) {
            if (confirm('¿Está seguro de eliminar este participante?')) {
                const participant = AppState.participants[index];
                
                // Liberar cupo
                AppState.slots.assigned[participant.categoria]--;
                
                // Eliminar participante
                AppState.participants.splice(index, 1);
                
                // Guardar cambios
                saveToLocalStorage();
                
                // Actualizar UI
                updateParticipantsTable();
                updateDashboardStats();
                updateSlotsInfo();
                checkRegistrationStatus();
            }
        }

        // Exportar participantes a CSV
        function exportParticipantsToCSV() {
            let csvContent = "data:text/csv;charset=utf-8,";
            csvContent += "Cargo,Nombre,Apellido,Email,Categoría,Fecha Registro\n";
            
            AppState.participants.forEach(participant => {
                const row = [
                    participant.cargo,
                    participant.nombre,
                    participant.apellido,
                    participant.email,
                    participant.categoria,
                    participant.fechaRegistro
                ].join(",");
                
                csvContent += row + "\n";
            });
            
            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", "participantes_congreso.csv");
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }

        // Manejar subida de agenda
        function handleAgendaUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            
            // Validar tipo y tamaño
            if (file.type !== 'application/pdf') {
                alert('Solo se permiten archivos PDF.');
                return;
            }
            
            if (file.size > 20 * 1024 * 1024) {
                alert('El archivo es demasiado grande. Máximo 20MB.');
                return;
            }
            
            // Guardar archivo en estado
            AppState.agenda = file;
            
            // Mostrar vista previa
            document.getElementById('agendaPreview').style.display = 'block';
            document.getElementById('agendaPreviewContent').innerHTML = `
                <p><strong>Archivo:</strong> ${file.name}</p>
                <p><strong>Tamaño:</strong> ${(file.size / 1024 / 1024).toFixed(2)} MB</p>
            `;
            
            // Guardar en localStorage (en una implementación real, esto se haría en el servidor)
            saveToLocalStorage();
        }

        // Sincronizar asistencias
        function syncAttendance() {
            // En una implementación completa, aquí se conectaría con Google Forms API
            // Por ahora, simulamos la sincronización
            
            // Simular datos de asistencias
            AppState.participants.forEach(participant => {
                // Asignar asistencias aleatorias para demostración
                participant.asistencias = {
                    day1: Math.random() > 0.3,
                    day2: Math.random() > 0.3,
                    day3: Math.random() > 0.3
                };
            });
            
            // Guardar cambios
            saveToLocalStorage();
            
            // Actualizar tabla
            updateAttendanceTable();
            
            alert('Asistencias sincronizadas correctamente.');
        }

        // Actualizar tabla de asistencias
        function updateAttendanceTable() {
            const tableBody = document.getElementById('attendanceTableBody');
            tableBody.innerHTML = '';
            
            AppState.participants.forEach(participant => {
                const asistencias = participant.asistencias || { day1: false, day2: false, day3: false };
                const totalAsistencias = (asistencias.day1 ? 1 : 0) + (asistencias.day2 ? 1 : 0) + (asistencias.day3 ? 1 : 0);
                const estado = totalAsistencias >= 2 ? 'Aprobado' : 'No Aprobado';
                const estadoClass = totalAsistencias >= 2 ? 'status-approved' : 'status-reproved';
                
                const row = document.createElement('tr');
                
                row.innerHTML = `
                    <td>${participant.cargo} ${participant.nombre} ${participant.apellido}</td>
                    <td>${asistencias.day1 ? '<span class="attendance-status status-approved">✓</span>' : '<span class="attendance-status status-reproved">✗</span>'}</td>
                    <td>${asistencias.day2 ? '<span class="attendance-status status-approved">✓</span>' : '<span class="attendance-status status-reproved">✗</span>'}</td>
                    <td>${asistencias.day3 ? '<span class="attendance-status status-approved">✓</span>' : '<span class="attendance-status status-reproved">✗</span>'}</td>
                    <td><span class="attendance-status ${estadoClass}">${estado}</span></td>
                `;
                
                tableBody.appendChild(row);
            });
        }

        // Exportar asistencias a CSV
        function exportAttendanceToCSV() {
            let csvContent = "data:text/csv;charset=utf-8,";
            csvContent += "Participante,Día 1,Día 2,Día 3,Total Asistencias,Estado\n";
            
            AppState.participants.forEach(participant => {
                const asistencias = participant.asistencias || { day1: false, day2: false, day3: false };
                const totalAsistencias = (asistencias.day1 ? 1 : 0) + (asistencias.day2 ? 1 : 0) + (asistencias.day3 ? 1 : 0);
                const estado = totalAsistencias >= 2 ? 'Aprobado' : 'No Aprobado';
                
                const row = [
                    `${participant.cargo} ${participant.nombre} ${participant.apellido}`,
                    asistencias.day1 ? 'Sí' : 'No',
                    asistencias.day2 ? 'Sí' : 'No',
                    asistencias.day3 ? 'Sí' : 'No',
                    totalAsistencias,
                    estado
                ].join(",");
                
                csvContent += row + "\n";
            });
            
            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", "asistencias_congreso.csv");
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }

        // Manejar subida de plantilla de certificados
        function handleCertificateTemplateUpload(event) {
            const file = event.target.files[0];
            if (!file) return;
            
            // Validar tipo
            if (!file.name.endsWith('.docx')) {
                alert('Solo se permiten archivos Word (.docx).');
                return;
            }
            
            // Guardar plantilla en estado
            AppState.certificateTemplate = file;
            
            // Mostrar vista previa
            document.getElementById('certificatePreview').style.display = 'block';
            document.getElementById('certificatePreviewContent').innerHTML = `
                <p><strong>Plantilla:</strong> ${file.name}</p>
                <p><strong>Campos dinámicos detectados:</strong> {{cargo}}, {{apellido}}, {{nombre}}</p>
            `;
            
            // Guardar en localStorage (en una implementación real, esto se haría en el servidor)
            saveToLocalStorage();
        }

        // Generar todos los certificados
        function generateAllCertificates() {
            if (!AppState.certificateTemplate) {
                alert('Primero debe cargar una plantilla de certificado.');
                return;
            }
            
            // En una implementación completa, aquí se procesaría la plantilla Word
            // y se generarían los PDFs para cada participante aprobado
            
            alert('Certificados generados correctamente. Los participantes aprobados podrán descargarlos desde la sección pública.');
        }

        // Cargar datos del localStorage
        function loadFromLocalStorage() {
            try {
                const savedParticipants = localStorage.getItem('congreso_participants');
                const savedSlots = localStorage.getItem('congreso_slots');
                const savedAgenda = localStorage.getItem('congreso_agenda');
                const savedAttendance = localStorage.getItem('congreso_attendance');
                const savedTemplate = localStorage.getItem('congreso_certificate_template');
                
                if (savedParticipants) {
                    AppState.participants = JSON.parse(savedParticipants);
                }
                
                if (savedSlots) {
                    AppState.slots = JSON.parse(savedSlots);
                }
                
                // En una implementación real, los archivos se manejarían de forma diferente
                // ya que localStorage no es adecuado para archivos grandes
            } catch (error) {
                console.error('Error al cargar datos del localStorage:', error);
            }
        }

        // Guardar datos en localStorage
        function saveToLocalStorage() {
            try {
                localStorage.setItem('congreso_participants', JSON.stringify(AppState.participants));
                localStorage.setItem('congreso_slots', JSON.stringify(AppState.slots));
                
                // En una implementación real, los archivos se guardarían en el servidor
                // o se usaría IndexedDB para almacenamiento local de archivos
            } catch (error) {
                console.error('Error al guardar datos en localStorage:', error);
            }
        }

        // Verificar si hay sesión admin activa al cargar la página
        function checkAdminSession() {
            const savedSession = sessionStorage.getItem('adminSession');
            if (savedSession) {
                AppState.adminSession = JSON.parse(savedSession);
                
                // Verificar si la sesión no ha expirado (30 minutos)
                const loginTime = new Date(AppState.adminSession.loginTime);
                const now = new Date();
                const sessionDuration = now - loginTime;
                
                if (sessionDuration < 30 * 60 * 1000) {
                    // Mostrar panel admin
                    document.getElementById('adminPanel').style.display = 'block';
                    document.querySelector('header').style.display = 'none';
                    document.querySelector('.hero').style.display = 'none';
                    document.querySelector('.info-section').style.display = 'none';
                    document.querySelector('.registration-section').style.display = 'none';
                    document.querySelector('.agenda-certificates').style.display = 'none';
                    document.querySelector('footer').style.display = 'none';
                    
                    // Configurar timeout de sesión restante
                    setTimeout(handleAdminLogout, 30 * 60 * 1000 - sessionDuration);
                } else {
                    // Sesión expirada
                    handleAdminLogout();
                }
            }
        }

        // Ejecutar verificación de sesión al cargar
        checkAdminSession();
    </script>
</body>
</html>
