<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Congreso Internacional Hospital Miguel H. Alcivar</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Open+Sans:wght@400;600&family=Roboto+Mono&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
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
            color: var(--dark-gray);
            background-color: var(--light-gray);
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        .header {
            background-color: var(--primary-blue);
            color: var(--white);
            padding: 1rem 0;
            border-bottom: 3px solid var(--secondary-blue);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .organizer-info h2 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .contact-info {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            font-size: 0.9rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .brochure-link {
            background-color: var(--secondary-blue);
            color: var(--white);
            padding: 0.5rem 1rem;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .brochure-link:hover {
            background-color: #1a4a7a;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--secondary-blue) 100%);
            color: var(--white);
            padding: 4rem 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .countdown {
            font-family: 'Roboto Mono', monospace;
            font-size: 2rem;
            margin: 2rem 0;
            background-color: rgba(0, 0, 0, 0.2);
            padding: 1rem;
            border-radius: 8px;
            display: inline-block;
        }

        .badges {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin: 1.5rem 0;
        }

        .badge {
            background-color: var(--countdown-orange);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .cta-button {
            display: inline-block;
            background-color: var(--success-green);
            color: var(--white);
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.2rem;
            margin-top: 1rem;
            transition: all 0.3s ease;
        }

        .cta-button:hover {
            background-color: #218838;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Cards Section */
        .cards-section {
            padding: 4rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-blue);
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .card {
            background-color: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card-header {
            background-color: var(--primary-blue);
            color: var(--white);
            padding: 1.5rem;
            text-align: center;
        }

        .card-body {
            padding: 1.5rem;
        }

        .card-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--primary-blue);
        }

        .capacity-counter {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-blue);
            margin: 1rem 0;
        }

        /* Registration Section */
        .registration-section {
            padding: 4rem 0;
            background-color: var(--medium-gray);
        }

        .registration-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        input, select {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--medium-gray);
            border-radius: 5px;
            font-family: 'Open Sans', sans-serif;
        }

        .submit-btn {
            width: 100%;
            padding: 1rem;
            background-color: var(--primary-blue);
            color: var(--white);
            border: none;
            border-radius: 5px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .submit-btn:hover {
            background-color: var(--secondary-blue);
        }

        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .alert {
            padding: 1rem;
            border-radius: 5px;
            margin: 1rem 0;
            font-weight: 600;
        }

        .alert-success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }

        .alert-error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }

        /* Admin Panel */
        .admin-panel {
            padding: 2rem 0;
            display: none;
        }

        .admin-tabs {
            display: flex;
            border-bottom: 1px solid var(--medium-gray);
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .admin-tab {
            padding: 1rem 2rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 600;
            border-bottom: 3px solid transparent;
        }

        .admin-tab.active {
            border-bottom: 3px solid var(--primary-blue);
            color: var(--primary-blue);
        }

        .admin-content {
            display: none;
        }

        .admin-content.active {
            display: block;
        }

        .btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: background-color 0.3s ease;
        }

        .btn-primary {
            background-color: var(--primary-blue);
            color: var(--white);
        }

        .btn-success {
            background-color: var(--success-green);
            color: var(--white);
        }

        .btn-danger {
            background-color: var(--alert-red);
            color: var(--white);
        }

        .btn-secondary {
            background-color: var(--medium-gray);
            color: var(--dark-gray);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            width: 90%;
            max-width: 400px;
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
                text-align: center;
            }

            .hero h1 {
                font-size: 1.8rem;
            }

            .countdown {
                font-size: 1.5rem;
            }

            .badges {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <div class="organizer-info">
                    <h2>UNIDAD DE DOCENCIA E INVESTIGACIÓN</h2>
                    <p>Hospital Miguel H. Alcivar</p>
                    <div class="contact-info">
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <span>docenciahmha2023@gmail.com</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <span>0991708712</span>
                        </div>
                    </div>
                </div>
                <a href="https://www.canva.com/design/DAGxPEDGSwU/hq3RFABqYJqYkuVMhQWBag/watch" target="_blank" class="brochure-link">
                    <i class="fas fa-book-open"></i>
                    Ver Información del Congreso
                </a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>I ER CONGRESO INTERNACIONAL DE ESPECIALIDADES CLINICAS-QUIRURGICAS</h1>
                <div class="countdown" id="countdown">
                    <span id="days">00</span>d <span id="hours">00</span>h <span id="minutes">00</span>m <span id="seconds">00</span>s
                </div>
                <div class="badges">
                    <div class="badge">GRATUITO</div>
                    <div class="badge">CUPOS LIMITADOS: 220</div>
                </div>
                <a href="#registration" class="cta-button">Registrarse Ahora</a>
            </div>
        </div>
    </section>

    <!-- Information Cards -->
    <section class="cards-section">
        <div class="container">
            <h2 class="section-title">Información Esencial</h2>
            <div class="cards-grid">
                <div class="card">
                    <div class="card-header">
                        <h3>Fechas</h3>
                    </div>
                    <div class="card-body">
                        <i class="fas fa-calendar-alt card-icon"></i>
                        <p>23-25 Octubre 2025</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>Lugar</h3>
                    </div>
                    <div class="card-body">
                        <i class="fas fa-map-marker-alt card-icon"></i>
                        <p>Auditorio ULEAM BAHIA DE CARAQUEZ</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>Capacidad</h3>
                    </div>
                    <div class="card-body">
                        <i class="fas fa-users card-icon"></i>
                        <p>220 cupos totales</p>
                        <div class="capacity-counter">
                            <span id="available-slots">220</span> cupos disponibles
                        </div>
                    </div>
                </div>
                <div class="card">
                    <div class="card-header">
                        <h3>Certificados</h3>
                    </div>
                    <div class="card-body">
                        <i class="fas fa-certificate card-icon"></i>
                        <p>Disponibles desde 27 Octubre 2025</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Registration Section -->
    <section class="registration-section" id="registration">
        <div class="container">
            <h2 class="section-title">Registro</h2>
            <div class="registration-form">
                <form id="registration-form">
                    <div class="form-group">
                        <label for="cargo">Cargo *</label>
                        <select id="cargo" name="cargo" required>
                            <option value="">Seleccione su cargo</option>
                            <option value="DR.">DR.</option>
                            <option value="DRA.">DRA.</option>
                            <option value="LCDO.">LCDO.</option>
                            <option value="LCDA.">LCDA.</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="nombre">Nombre *</label>
                        <input type="text" id="nombre" name="nombre" required>
                    </div>
                    <div class="form-group">
                        <label for="apellido">Apellido *</label>
                        <input type="text" id="apellido" name="apellido" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email *</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="categoria">Categoría *</label>
                        <select id="categoria" name="categoria" required>
                            <option value="">Seleccione su categoría</option>
                            <option value="Médico General">Médico General</option>
                            <option value="Especialista">Especialista</option>
                            <option value="Otro">Otro</option>
                        </select>
                    </div>
                    <button type="submit" class="submit-btn" id="submit-btn">
                        <span id="submit-text">Registrarse</span>
                        <div class="loading" id="submit-loading" style="display: none;"></div>
                    </button>
                </form>
                <div id="registration-message"></div>
            </div>
        </div>
    </section>

    <!-- Admin Login -->
    <div class="container" style="text-align: center; margin: 2rem 0;">
        <button id="admin-login-btn" class="btn btn-primary">Acceso Administrativo</button>
    </div>

    <!-- Admin Panel -->
    <section class="admin-panel" id="admin-panel">
        <div class="container">
            <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 2rem;">
                <h2>Panel de Administración</h2>
                <button id="admin-logout" class="btn btn-secondary">Cerrar Sesión</button>
            </div>
            
            <div class="admin-tabs">
                <button class="admin-tab active" data-tab="participants">Participantes</button>
                <button class="admin-tab" data-tab="attendance">Asistencias</button>
            </div>
            
            <div class="admin-content active" id="participants-content">
                <h3>Gestión de Participantes</h3>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin-bottom: 2rem;">
                    <div style="background: white; padding: 1.5rem; border-radius: 8px; text-align: center;">
                        <div style="font-size: 2rem; font-weight: bold; color: var(--primary-blue);" id="total-slots">220</div>
                        <div>Cupos Totales</div>
                    </div>
                    <div style="background: white; padding: 1.5rem; border-radius: 8px; text-align: center;">
                        <div style="font-size: 2rem; font-weight: bold; color: var(--primary-blue);" id="assigned-slots">0</div>
                        <div>Registrados</div>
                    </div>
                </div>
                
                <div style="background: white; padding: 2rem; border-radius: 10px; margin-bottom: 2rem;">
                    <h4>Registrar Participante</h4>
                    <form id="admin-registration-form" style="display: grid; gap: 1rem;">
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                            <div class="form-group">
                                <label for="admin-cargo">Cargo</label>
                                <select id="admin-cargo" name="cargo" required>
                                    <option value="DR.">DR.</option>
                                    <option value="DRA.">DRA.</option>
                                    <option value="LCDO.">LCDO.</option>
                                    <option value="LCDA.">LCDA.</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="admin-categoria">Categoría</label>
                                <select id="admin-categoria" name="categoria" required>
                                    <option value="Médico General">Médico General</option>
                                    <option value="Especialista">Especialista</option>
                                    <option value="Otro">Otro</option>
                                </select>
                            </div>
                        </div>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                            <div class="form-group">
                                <label for="admin-nombre">Nombre</label>
                                <input type="text" id="admin-nombre" name="nombre" required>
                            </div>
                            <div class="form-group">
                                <label for="admin-apellido">Apellido</label>
                                <input type="text" id="admin-apellido" name="apellido" required>
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="admin-email">Email</label>
                            <input type="email" id="admin-email" name="email" required>
                        </div>
                        <button type="submit" class="btn btn-primary">
                            <span id="admin-submit-text">Registrar Participante</span>
                            <div class="loading" id="admin-submit-loading" style="display: none;"></div>
                        </button>
                    </form>
                </div>
                
                <div style="background: white; padding: 2rem; border-radius: 10px;">
                    <h4>Lista de Participantes</h4>
                    <div id="participants-list">
                        <!-- Los participantes se cargarán aquí -->
                    </div>
                </div>
            </div>
            
            <div class="admin-content" id="attendance-content">
                <h3>Control de Asistencias</h3>
                <p>Módulo de control de asistencias - En desarrollo</p>
            </div>
        </div>
    </section>

    <!-- Login Modal -->
    <div class="modal" id="login-modal">
        <div class="modal-content">
            <div style="margin-bottom: 1.5rem; text-align: center;">
                <span style="float: right; font-size: 1.5rem; cursor: pointer;" class="close-modal">&times;</span>
                <h2>Acceso Administrativo</h2>
            </div>
            <form id="login-form">
                <div class="form-group">
                    <label for="username">Usuario</label>
                    <input type="text" id="username" name="username" required>
                </div>
                <div class="form-group">
                    <label for="password">Contraseña</label>
                    <input type="password" id="password" name="password" required>
                </div>
                <button type="submit" class="submit-btn">
                    <span id="login-submit-text">Iniciar Sesión</span>
                    <div class="loading" id="login-submit-loading" style="display: none;"></div>
                </button>
            </form>
        </div>
    </div>

    <script>
        // Configuración de Supabase
        const SUPABASE_URL = 'https://smihcuhfgyjtwuaatfak.supabase.co';
        const SUPABASE_ANON_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InNtaWhjdWhmZ3lqdHd1YWF0ZmFrIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NjA3MTAwODksImV4cCI6MjA3NjI4NjA4OX0.HQuTOSon8hCpkhxAp-tI3W28j7w7j7uVidV9i6-HpfE';
        
        const supabase = window.supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);
        
        let participants = [];
        let adminLoggedIn = false;
        const totalSlots = 220;

        // Elementos DOM
        const countdownElement = document.getElementById('countdown');
        const availableSlotsElement = document.getElementById('available-slots');
        const registrationForm = document.getElementById('registration-form');
        const submitBtn = document.getElementById('submit-btn');
        const submitText = document.getElementById('submit-text');
        const submitLoading = document.getElementById('submit-loading');
        const registrationMessage = document.getElementById('registration-message');
        const adminLoginBtn = document.getElementById('admin-login-btn');
        const adminPanel = document.getElementById('admin-panel');
        const adminLogout = document.getElementById('admin-logout');
        const loginModal = document.getElementById('login-modal');
        const closeModal = document.querySelector('.close-modal');
        const loginForm = document.getElementById('login-form');
        const adminRegistrationForm = document.getElementById('admin-registration-form');
        const participantsList = document.getElementById('participants-list');
        const totalSlotsElement = document.getElementById('total-slots');
        const assignedSlotsElement = document.getElementById('assigned-slots');
        const adminTabs = document.querySelectorAll('.admin-tab');
        const adminContents = document.querySelectorAll('.admin-content');

        // Inicialización
        async function init() {
            updateCountdown();
            setInterval(updateCountdown, 1000);
            
            await loadParticipants();
            updateAvailableSlots();
            updateRegistrationButton();
            
            // Event listeners
            registrationForm.addEventListener('submit', handleRegistration);
            adminLoginBtn.addEventListener('click', () => loginModal.style.display = 'flex');
            closeModal.addEventListener('click', () => loginModal.style.display = 'none');
            loginForm.addEventListener('submit', handleAdminLogin);
            adminLogout.addEventListener('click', handleAdminLogout);
            adminRegistrationForm.addEventListener('submit', handleAdminRegistration);
            
            // Tabs administrativos
            adminTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.getAttribute('data-tab');
                    switchAdminTab(tabId);
                });
            });
            
            checkAdminSession();
        }

        function updateCountdown() {
            const now = new Date();
            const targetDate = new Date('2025-10-23T08:00:00');
            const timeRemaining = targetDate - now;
            
            if (timeRemaining <= 0) {
                countdownElement.innerHTML = "¡El congreso ha comenzado!";
                return;
            }
            
            const days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
        }

        function updateAvailableSlots() {
            const assigned = participants.length;
            const available = Math.max(0, totalSlots - assigned);
            availableSlotsElement.textContent = available;
            assignedSlotsElement.textContent = assigned;
            totalSlotsElement.textContent = totalSlots;
        }

        function updateRegistrationButton() {
            const now = new Date();
            const registrationDeadline = new Date('2025-10-22T23:59:00');
            
            if (now > registrationDeadline) {
                submitBtn.disabled = true;
                submitText.textContent = 'Inscripciones Cerradas';
            } else if (participants.length >= totalSlots) {
                submitBtn.disabled = true;
                submitText.textContent = 'No Disponible';
            } else {
                submitBtn.disabled = false;
                submitText.textContent = 'Registrarse';
            }
        }

        async function handleRegistration(e) {
            e.preventDefault();
            
            const formData = new FormData(registrationForm);
            const cargo = formData.get('cargo');
            const nombre = formData.get('nombre');
            const apellido = formData.get('apellido');
            const email = formData.get('email');
            const categoria = formData.get('categoria');
            
            // Validaciones
            if (participants.some(p => p.email === email)) {
                showMessage('Este email ya está registrado.', 'error');
                return;
            }
            
            if (participants.length >= totalSlots) {
                showMessage('No hay cupos disponibles.', 'error');
                return;
            }

            // Loading state
            submitText.style.display = 'none';
            submitLoading.style.display = 'inline-block';
            submitBtn.disabled = true;

            try {
                const { data, error } = await supabase
                    .from('participants')
                    .insert([{ cargo, nombre, apellido, email, categoria }])
                    .select();

                if (error) throw error;

                participants.push({
                    id: data[0].id,
                    cargo,
                    nombre,
                    apellido,
                    email,
                    categoria,
                    fechaRegistro: data[0].fecha_registro
                });

                updateAvailableSlots();
                updateRegistrationButton();
                showMessage('¡Registro exitoso! Te esperamos en el congreso.', 'success');
                registrationForm.reset();
            } catch (error) {
                console.error('Error:', error);
                showMessage('Error al registrar. Intente nuevamente.', 'error');
            } finally {
                submitText.style.display = 'inline-block';
                submitLoading.style.display = 'none';
                submitBtn.disabled = false;
            }
        }

        function showMessage(message, type) {
            registrationMessage.innerHTML = '';
            const alertDiv = document.createElement('div');
            alertDiv.className = `alert alert-${type === 'success' ? 'success' : 'error'}`;
            alertDiv.textContent = message;
            registrationMessage.appendChild(alertDiv);
            
            setTimeout(() => {
                registrationMessage.innerHTML = '';
            }, 5000);
        }

        async function handleAdminLogin(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            if (username === 'DOCENCIA' && password === 'DOCENCIA') {
                adminLoggedIn = true;
                sessionStorage.setItem('adminLoggedIn', 'true');
                adminPanel.style.display = 'block';
                loginModal.style.display = 'none';
                updateAdminDashboard();
            } else {
                alert('Credenciales incorrectas');
            }
        }

        function handleAdminLogout() {
            adminLoggedIn = false;
            sessionStorage.removeItem('adminLoggedIn');
            adminPanel.style.display = 'none';
        }

        function checkAdminSession() {
            if (sessionStorage.getItem('adminLoggedIn') === 'true') {
                adminLoggedIn = true;
                adminPanel.style.display = 'block';
                updateAdminDashboard();
            }
        }

        function switchAdminTab(tabId) {
            adminTabs.forEach(tab => {
                if (tab.getAttribute('data-tab') === tabId) {
                    tab.classList.add('active');
                } else {
                    tab.classList.remove('active');
                }
            });
            
            adminContents.forEach(content => {
                if (content.id === `${tabId}-content`) {
                    content.classList.add('active');
                } else {
                    content.classList.remove('active');
                }
            });
        }

        async function handleAdminRegistration(e) {
            e.preventDefault();
            
            const formData = new FormData(adminRegistrationForm);
            const cargo = formData.get('cargo');
            const nombre = formData.get('nombre');
            const apellido = formData.get('apellido');
            const email = formData.get('email');
            const categoria = formData.get('categoria');

            if (participants.some(p => p.email === email)) {
                alert('Este email ya está registrado.');
                return;
            }

            try {
                const { data, error } = await supabase
                    .from('participants')
                    .insert([{ cargo, nombre, apellido, email, categoria }])
                    .select();

                if (error) throw error;

                participants.push({
                    id: data[0].id,
                    cargo,
                    nombre,
                    apellido,
                    email,
                    categoria,
                    fechaRegistro: data[0].fecha_registro
                });

                updateAvailableSlots();
                updateRegistrationButton();
                updateAdminDashboard();
                adminRegistrationForm.reset();
                alert('Participante registrado exitosamente.');
            } catch (error) {
                console.error('Error:', error);
                alert('Error al registrar participante.');
            }
        }

        function updateAdminDashboard() {
            renderParticipantsList();
        }

        function renderParticipantsList() {
            participantsList.innerHTML = '';
            
            if (participants.length === 0) {
                participantsList.innerHTML = '<p>No hay participantes registrados</p>';
                return;
            }
            
            participants.forEach(participant => {
                const participantDiv = document.createElement('div');
                participantDiv.style.cssText = 'padding: 1rem; border-bottom: 1px solid #eee;';
                participantDiv.innerHTML = `
                    <strong>${participant.cargo} ${participant.nombre} ${participant.apellido}</strong><br>
                    <small>${participant.email} - ${participant.categoria}</small>
                    <button onclick="deleteParticipant('${participant.id}')" class="btn btn-danger" style="float: right; margin-left: 0.5rem;">Eliminar</button>
                `;
                participantsList.appendChild(participantDiv);
            });
        }

        async function deleteParticipant(id) {
            if (confirm('¿Está seguro de eliminar este participante?')) {
                try {
                    const { error } = await supabase
                        .from('participants')
                        .delete()
                        .eq('id', id);

                    if (error) throw error;

                    participants = participants.filter(p => p.id !== id);
                    updateAvailableSlots();
                    updateRegistrationButton();
                    updateAdminDashboard();
                } catch (error) {
                    console.error('Error:', error);
                    alert('Error al eliminar participante.');
                }
            }
        }

        async function loadParticipants() {
            try {
                const { data, error } = await supabase
                    .from('participants')
                    .select('*')
                    .order('fecha_registro', { ascending: false });

                if (error) throw error;

                if (data) {
                    participants = data.map(p => ({
                        id: p.id,
                        cargo: p.cargo,
                        nombre: p.nombre,
                        apellido: p.apellido,
                        email: p.email,
                        categoria: p.categoria,
                        fechaRegistro: p.fecha_registro
                    }));
                }
            } catch (error) {
                console.error('Error al cargar participantes:', error);
            }
        }

        // Hacer funciones globales
        window.deleteParticipant = deleteParticipant;

        // Inicializar
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
